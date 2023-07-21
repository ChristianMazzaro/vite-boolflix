<script >
import { store } from '../store.js'
import singleList from './singleList.vue'

  export default {
    components:{
        singleList,
    },
    data(){
      return{
        // vote: 0,
        store,
      }
    },
    methods:{
        // LangFlag(lang){
        //     if(lang == 'it'){
        //         return 'https://flagicons.lipis.dev/flags/4x3/it.svg';
        //     }

        //     else if(lang == 'en'){
        //         return 'https://flagicons.lipis.dev/flags/4x3/gb.svg';
        //     }

        //     else if(lang == 'fr'){
        //         return 'https://flagicons.lipis.dev/flags/4x3/fr.svg';
        //     }

        //     else if(lang == 'es'){
        //         return 'https://flagicons.lipis.dev/flags/4x3/es.svg';
        //     }

        //     else if(lang == 'de'){
        //         return 'https://flagicons.lipis.dev/flags/4x3/de.svg';
        //     }

        //     else if(lang == 'ja'){
        //         return 'https://flagicons.lipis.dev/flags/4x3/jp.svg';
        //     }

        //     else{
        //         return 'https://flagicons.lipis.dev/flags/4x3/xx.svg';
        //     }
        // },

        // getThumbs(elem){
        //     return store.seriesThumbs + elem
        // },

        // voteAdj(elem){
        //     this.vote = parseInt(elem)
        //     if(this.vote == 1 || this.vote == 2){
        //         return this.vote = 1
        //     }

        //     else if(this.vote == 3 || this.vote == 4){
        //         return this.vote = 2
        //     }

        //     else if(this.vote == 5 || this.vote == 6){
        //         return this.vote = 3
        //     }

        //     else if(this.vote == 7 || this.vote == 8){
        //         return this.vote = 4
        //     }

        //     else if(this.vote == 9 || this.vote == 10){
        //         return this.vote = 5
        //     }

        //     else{
        //         return this.vote = 0
        //     }
        // },  

    }
  }
</script>

<template>
    <main>
        
        <h1>
            film
        </h1>
        <ul>
            <li class="movie_container" v-for="(movie, i) in store.movies" :key="i">
                <singleList :listData="movie"/>
            </li>
        </ul>

        <h1>
            Serie tv
        </h1>
        <ul>
            <li class="movie_container" v-for="(series, i) in store.tvSeries" :key="i">
                <singleList :listData="series"/>
                <!-- <img class="thumb" :src="getThumbs(series.poster_path)" :alt="series.name">
                <ul class="movie-info">
                    <li>
                        {{ series.name }}
                    </li>
                    <li>
                        {{ series.original_name }}
                    </li>
                    <li>
                        <img class="flag" :src="LangFlag(series.original_language)" alt="">
                        {{ series.original_language }}
                    </li>
                    <li v-if="voteAdj(series.vote_average)">
                        <span v-if="vote==1">
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-regular fa-star"></i>
                            <i class="fa-regular fa-star"></i>
                            <i class="fa-regular fa-star"></i>
                            <i class="fa-regular fa-star"></i>
                        </span>
                        <span v-if="vote==2">
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-regular fa-star"></i>
                            <i class="fa-regular fa-star"></i>
                            <i class="fa-regular fa-star"></i>
                        </span>
                        <span v-if="vote==3">
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-regular fa-star"></i>
                            <i class="fa-regular fa-star"></i>
                        </span>
                        <span v-if="vote==4">
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-regular fa-star"></i>
                        </span>
                        <span v-if="vote==5">
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-solid fa-star"></i>
                        </span>
                        {{ vote }}
                    </li>
                </ul> -->
            </li>
        </ul>
    </main>
</template>

<style lang="scss" scoped>

    .movie_container{
        display: flex;
        margin-bottom: 20px;
    }

    li{
      list-style: none;
      background-color: black;
      color: white;

      .flag{
        width: 20px;
      }

      .thumb{
        width: 100px;
      }

      i{
        color: yellow;
      }
    }
</style>
