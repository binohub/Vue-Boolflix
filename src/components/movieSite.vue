<template>

    <div class="row">
        <div class="filmHeader col-12">
            <h2 v-if="propFilmResultArray.length">Movies Founded</h2>
            <h2 v-if="propFilmResultArray.length === 0">Search a Movie</h2>

            <!-- <ul>
                <li class="col-3">
                    Title
                </li>
                <li class="col-3">
                    Original Title
                </li>
                <li class="col-3">
                    Original Language
                </li>
                <li class="col-3">
                    Vote Count
                </li>
            </ul> -->
        </div>
        <div v-for="film in propFilmResultArray" :key="film.id" class="netCard col-2">

            <div class="cardUp position-relative">
                <img class="img-fluid" :src="`${imgUrl}${film.poster_path}`" alt="poster">
                <div class="cardDown position-absolute">
                    <ul>
                        <li class="">
                            <span class="descCard">TITOLO:</span>{{ film.title }}
                        </li>
                        <li class="">
                            <span class="descCard">TITOLO ORIGINALE:</span>{{ film.original_title }}
                        </li>
                        <li class="">
                            <img class="img-fluid" :src="`${langUrl}${film.original_language}.png`" alt="">
                        </li>
                        <li class="">
                            <span v-for="n in 5" :key="n"
                                :class="n <= functionHalf(film.vote_average) ? 'yellowStar' : 'darkStar'"> ✩ </span>
                            <!-- <span v-for="n in functionHalf(film.vote_average)" :key='n'> ⭐ </span> -->
                        </li>
                    </ul>
                </div>
            </div>



        </div>
    </div>

</template>





<script>
export default {
    props: {
        propFilmResultArray: Array,
    },



    data() {
        return {
            imgUrl: "https://image.tmdb.org/t/p/w342/",
            langUrl: "../../public/lang/",
        }
    },

    methods: {
        functionHalf(vote) {
            return Math.max(Math.ceil(vote / 2), 1)
        },
    }
}
</script>





<style scoped lang="scss">
</style>
