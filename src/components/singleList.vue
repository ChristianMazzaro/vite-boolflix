<script >
import { store } from '../store.js'

  export default {
    components:{

    },
    data(){
      return{
        store,
        vote: 0,
      }
    },
    methods:{
        getThumbs(){
            return store.seriesThumbs + this.listData.poster_path
        },

        LangFlag(){
            if(this.listData.original_language == 'it'){
                return 'https://flagicons.lipis.dev/flags/4x3/it.svg';
            }

            else if(this.listData.original_language == 'en'){
                return 'https://flagicons.lipis.dev/flags/4x3/gb.svg';
            }

            else if(this.listData.original_language == 'fr'){
                return 'https://flagicons.lipis.dev/flags/4x3/fr.svg';
            }

            else if(this.listData.original_language == 'es'){
                return 'https://flagicons.lipis.dev/flags/4x3/es.svg';
            }

            else if(this.listData.original_language == 'de'){
                return 'https://flagicons.lipis.dev/flags/4x3/de.svg';
            }

            else if(this.listData.original_language == 'ja'){
                return 'https://flagicons.lipis.dev/flags/4x3/jp.svg';
            }

            else{
                return 'https://flagicons.lipis.dev/flags/4x3/xx.svg';
            }
        },

        voteAdj(elem){
            this.vote = parseInt(elem)
            if(this.vote == 1 || this.vote == 2){
                return this.vote = 1
            }

            else if(this.vote == 3 || this.vote == 4){
                return this.vote = 2
            }

            else if(this.vote == 5 || this.vote == 6){
                return this.vote = 3
            }

            else if(this.vote == 7 || this.vote == 8){
                return this.vote = 4
            }

            else if(this.vote == 9 || this.vote == 10){
                return this.vote = 5
            }

            else{
                return this.vote = 0
            }
        },  
    },
    props: {
        listData:{
            type:Object,
            default:null,
        }
    },

    computed:{

    },
  }
</script>

<template>
    <img class="thumb" :src="getThumbs()" :alt="listData.title">
    <ul class="movie-info">
        <li>
            {{ listData.title ?? listData.name }}
        </li>
        <li>
            {{ listData.original_title ?? listData.original_name }}
        </li>
        <li>
            <img class="flag" :src="LangFlag()" alt="">
            {{ listData.original_language }}
        </li>
        <li v-if="voteAdj(listData.vote_average)">
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
    </ul>
</template>

<style lang="scss" scoped>

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
