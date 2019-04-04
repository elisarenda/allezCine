<template>
    <div id="series">
        <h2 class='title'>Series</h2>
        <div class="container">
            <FilmCard v-for="(i, index) in 10" :key='index' :film="resultsSer[i-1]" />
        </div>
    </div>
</template>

<script>

import { getDataTmdb } from '../../apis/tmdbApi/tmdbApiMethods.js'
import FilmCard from '../components/FilmCard.vue'

export default {
    name: 'series',
    components: {
        FilmCard
    },
    data () {
        return {
            resultsSer: null
        }
    },
    created () {
        this.resultsSer = getDataTmdb('tv', 'en', 'popularity.desc', '1')
    }
}
</script>

<style>
#main {
    /* background-color: rgb(255, 255, 255); */
}

.title {
    margin: 60px 150px 40px 150px;
    text-align: left;
    border-left: 5px solid red;
    padding-left: 10px;
}

.center {
    display: block;
    margin: auto;
}

.container {
    margin: 20px 200px;
    display: flex;
    flex-flow: row wrap;
}

</style>
