<script >
import axios from 'axios';
import { store } from './store.js'
import AppHeader from '../src/components/AppHeader.vue'
import AppMain from '../src/components/AppMain.vue'

  export default {
    components:{
      AppHeader,
      AppMain,
    },
    data(){
      return{
        store
      }
    },
    methods:{
      startSearch(){
        

        axios
          .get('https://api.themoviedb.org/3/search/movie', {
            params:{
              api_key: 'bf4fd15b528c50cc3aba5a346e201b7f',
              query: this.store.searchtext,
            }
          })

          .then(response =>{
            console.log(response.data)
            this.store.movies = response.data.results;
          });

        axios
          .get('https://api.themoviedb.org/3/search/tv',{
            params:{
              api_key: 'bf4fd15b528c50cc3aba5a346e201b7f',
              query: this.store.searchtext,
            }
          })

          .then(response =>{
            console.log(response.data)
            this.store.tvSeries = response.data.results;
          });

      }
    }
  }
</script>

<template>
  <head>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap" rel="stylesheet">
  </head>
  <AppHeader @MovieSearch="startSearch()" />
  <AppMain />
</template>

<style lang="scss">
@use '../src/assets/scss/main.scss'


</style>
