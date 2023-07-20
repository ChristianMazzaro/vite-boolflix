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
        }
    }
  }
</script>

<template>
    <main>
        <h1>
            film
        </h1>
        <ul>
            <li v-for="(movie, i) in store.movies" :key="i">
                <ul class="movie-info">
                    <li>
                    {{ movie.title }}
                    </li>
                    <li>
                    {{ movie.original_title }}
                    </li>
                    <li>
                        <img :src="LangFlag(movie.original_language)" alt="">
                    {{ movie.original_language }}
                    </li>
                    <li>
                    {{ movie.vote_average }}
                    </li>
                </ul>
                 <hr>
            </li>
        </ul>

        <h1>
            Serie tv
        </h1>
        <ul>
            <li v-for="(series, i) in store.tvSeries" :key="i">
                <ul class="movie-info">
                    <li>
                    {{ series.name }}
                    </li>
                    <li>
                    {{ series.original_name }}
                    </li>
                    <li>
                        <img :src="LangFlag(series.original_language)" alt="">
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



    li{
      list-style: none;
      background-color: rgb(90, 163, 90);

      img{
        width: 20px;
      }
    }
</style>
