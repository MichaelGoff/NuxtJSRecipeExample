<template>
    <section class="single-recipe">
        <h1>{{ recipe.title }}</h1>
        <div>
            <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title" />
        </div>
        <p>{{recipe.descriptionText}}</p>
    </section>
</template>

<script>
export default {
    asyncData(context) {
        return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    recipe: [
                        {
                            id: "1",
                            title: "Delicious Pizza",
                            previewText: "Awesome Pizza!",
                            descriptionText: "this is the description 1",
                            thumbnail: "https://img.huffingtonpost.com/asset/585be1aa1600002400bdf2a6.jpeg?ops=scalefit_970_noupscale"
                        },
                        {
                            id: "2",
                            title: "seafood salad",
                            previewText: "very tasty indeed",
                            descriptionText: "this is the description 2",
                            thumbnail: "https://img.huffingtonpost.com/asset/585be1aa1600002400bdf2a6.jpeg?ops=scalefit_970_noupscale"
                        }
                    ].find(el => el.id === context.params.id)
                });
            }, 1500);
        });
    },
}
</script>


<style>
.single-recipe {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
}

.recipe-image {
    width: 100%;
    
}
</style>

