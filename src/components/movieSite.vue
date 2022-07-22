<template>

    <div id="movieSite">

        <div class="filmHeader">

            <div class="col-12">
                <h2>Movies</h2>
            </div>
            <ul>
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
            </ul>

        </div>


        <ul v-for="film in propFilmResultArray" :key="film.id">
            <li class="col-3">
                {{ film.title }}
            </li>
            <li class="col-3">
                {{ film.original_title }}
            </li>
            <li class="col-3">
                {{ film.original_language }}
            </li>
            <li class="col-3">
                {{ film.vote_count }}
            </li>
        </ul>

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
