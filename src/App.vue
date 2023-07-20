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
        alert(this.store.searchtext)

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
  <AppHeader @MovieSearch="startSearch()" />
  <AppMain />
    <footer>
      <i class="fa-solid fa-house"></i>
    </footer>

</template>

<style lang="scss">
@use '../src/assets/scss/main.scss'


</style>
