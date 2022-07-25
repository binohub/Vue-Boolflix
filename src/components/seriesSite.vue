<template>

    <div class="row">
        <div class="seriesHeader col-12">
            <h2 v-if="propTvResultArray.length">Tv Shows Founded</h2>
            <h2 v-if="propTvResultArray.length === 0">Search a Tv Show</h2>
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
        <div v-for="tv in propTvResultArray" :key="tv.id" class="col-2">

            <div class="cardUp">
                <img class="img-fluid" :src="imgUrl + tv.poster_path" alt="poster">
            </div>

            <div class="cardDown">
                <ul>
                    <li class="">
                        {{ tv.name }}
                    </li>
                    <li class="">
                        {{ tv.original_name }}
                    </li>
                    <li class="">
                        {{ tv.original_language }}
                    </li>
                    <li class="">
                        <span v-for="n in 5" :key="n" 
                        :class= " n <= functionHalf(tv.vote_average) ? 'yellowStar' : 'darkStar' "> ✩ </span>
                    </li>
                </ul>
            </div>

        </div>
    </div>

</template>





<script>
export default {
    props: {
        propTvResultArray: Array,
    },



    data() {
        return {
            imgUrl: "https://image.tmdb.org/t/p/w342/",
        }
    },
    methods: {
        functionHalf(vote) {
            return Math.max(Math.ceil(vote / 2), 1)
        },
    }
}
</script>





<style lang="scss">
</style>
