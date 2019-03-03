<template>
    <section class="recipes">
        <Recipe 
            v-for="recipe in recipes"
            :key="recipe.id"
            :thumbnail="recipe.thumbnail"
            :title="recipe.title"
            :id="recipe.id"
            :previewText="recipe.previewText"
        />
    </section>
</template>

<script>
import Recipe from '@/components/Recipe';

export default {
    components: {
        Recipe,
    },
    asyncData() {
        return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    recipes: [
                        {
                            id: "1",
                            title: "Delicious Pizza",
                            previewText: "Awesome Pizza!",
                            thumbnail: "https://img.huffingtonpost.com/asset/585be1aa1600002400bdf2a6.jpeg?ops=scalefit_970_noupscale"
                        },
                        {
                            id: "2",
                            title: "seafood salad",
                            previewText: "very tasty indeed",
                            thumbnail: "https://img.huffingtonpost.com/asset/585be1aa1600002400bdf2a6.jpeg?ops=scalefit_970_noupscale"
                        }
                    ]
                });
            }, 1500);
        });
    },
}
</script>


<style scoped>
.recipes {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
}

</style>