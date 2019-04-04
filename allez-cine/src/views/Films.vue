<template>
    <div id="film">
        <h2 class='title'>Films</h2>
        <div class="container">
            <FilmCard v-for="(i, index) in 20" :key='index' :film="resultsMov[i]" />
        </div>
    </div>
</template>

<script>

import { getDataTmdb } from '../../apis/tmdbApi/tmdbApiMethods.js'
import FilmCard from '../components/FilmCard.vue'

export default {
   name: 'film',
    components: {
        FilmCard
    },
    data () {
        return {
            resultsMov: null,
        }
    },
    created () {
        this.resultsMov = getDataTmdb('movie', 'en', 'popularity.desc', '1')
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
