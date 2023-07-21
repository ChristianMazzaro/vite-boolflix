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
            this.vote = Math.ceil(elem / 2)
            console.log(this.vote)
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
        <li>
            <span v-for="number in vote" :key="number">
                <i class="fa-solid fa-star"></i>
            </span>
            <span v-for="number in (5 - vote)" :key="number">
                <i class="fa-regular fa-star"></i>
            </span>
            
        </li>
        <li>
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
