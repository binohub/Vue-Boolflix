<template>

    <div class="row">
        <div class="filmHeader col-12">
            <h2>Movies</h2>
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
        <div v-for="film in propFilmResultArray" :key="film.id" class="col-3">

            <div class="cardUp">
                <img class="img-fluid" :src="`https://image.tmdb.org/t/p/w342/${film.poster_path}`" alt="poster">
            </div>

            <div class="cardDown">
                <ul>
                    <li class="">
                        {{ film.title }}
                    </li>
                    <li class="">
                        {{ film.original_title }}
                    </li>
                    <li class="">
                        {{ film.original_language }}
                    </li>
                    <li class="">
                        {{ film.vote_count }}
                    </li>
                </ul>
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
        }
    },
}
</script>





<style scoped lang="scss">
</style>
