<script >
import axios from 'axios';
import { store } from '../store.js'

  export default {
    components:{

    },
    data(){
      return{
        store
      }
    },
    methods:{
        LangFlag(lang){
            if(lang == 'it'){
                return 'https://flagicons.lipis.dev/flags/4x3/it.svg';
            }

            else if(lang == 'en'){
                return 'https://flagicons.lipis.dev/flags/4x3/gb.svg';
            }

            else if(lang == 'fr'){
                return 'https://flagicons.lipis.dev/flags/4x3/fr.svg';
            }

            else if(lang == 'es'){
                return 'https://flagicons.lipis.dev/flags/4x3/es.svg';
            }

            else if(lang == 'de'){
                return 'https://flagicons.lipis.dev/flags/4x3/de.svg';
            }

            else if(lang == 'ja'){
                return 'https://flagicons.lipis.dev/flags/4x3/jp.svg';
            }

            else{
                return 'https://flagicons.lipis.dev/flags/4x3/xx.svg';
            }
        },

        getThumbs(elem){
            return store.seriesThumbs + elem
        },

        voteAdj(){
           integer = parseInt(store.movies.vote_average)
            if(integer == 1 || integer == 2){
                return vote = 1
            }

            else if(integer == 3 || integer == 4){
                return vote = 2
            }

            else if(integer == 5 || integer == 6){
                return vote = 3
            }

            else if(integer == 7 || integer == 8){
                return vote = 4
            }

            else if(integer == 9 || integer == 10){
                return vote = 5
            }
        },  

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
                <img class="thumb" :src="getThumbs(movie.poster_path)" :alt="movie.title">
                <ul class="movie-info">
                    <li>
                        {{ movie.title }}
                    </li>
                    <li>
                        {{ movie.original_title }}
                    </li>
                    <li>
                        <img class="flag" :src="LangFlag(movie.original_language)" alt="">
                        {{ movie.original_language }}
                    </li>
                    <li>
                        {{ movie.vote_average }}
                    </li>
                </ul>
                 
            </li>
        </ul>

        <h1>
            Serie tv
        </h1>
        <ul>
            <li class="movie_container" v-for="(series, i) in store.tvSeries" :key="i">
                <img class="thumb" :src="getThumbs(series.poster_path)" :alt="series.name">
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
                    <li>
                        {{ series.vote_average }}
                    </li>
                </ul>
                <hr>
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
      background-color: rgb(90, 163, 90);

      .flag{
        width: 20px;
      }

      .thumb{
        width: 100px;
      }
    }
</style>
