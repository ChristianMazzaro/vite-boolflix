<script >

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

    }
  }
</script>

<template>
    <header>

      <div class="form-container">
         <input v-model="store.searchtext" type="text" placeholder="inserisci il nome di un film od una serie tv...">
         <button @click="$emit('MovieSearch')">cerca</button>
      </div>

    </header>
</template>

<style lang="scss" scoped>

</style>
