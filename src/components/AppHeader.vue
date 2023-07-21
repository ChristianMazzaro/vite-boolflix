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
      <div class="nav">
        <div class="logo">
          <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRFZPJow3u_gaTyP2YJmUfKaYfgVm_4WswVyYMXcgo9IVD2mMZnNR_sZccClGYpY3ZsJsg&usqp=CAU" alt="">
        </div>

        <div class="form-container">
          <input v-model="store.searchtext" type="text" placeholder="inserisci il nome di un film od una serie tv...">
          <button @click="$emit('MovieSearch')">Invio</button>
        </div>
      </div>
    </header>
    <hr style="color: darkred;">
</template>

<style lang="scss" scoped>
  .nav{
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: black;
    height: 90px;
    width: 100vw;

    .logo{
      padding-left: 80px;
      width: 100%;
      height: 100%;
      img{
        height: 100%;
      }

    }

    .form-container{
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: space-around;

      input{
        width: 35%;
        border-radius: 8px;
        color: white;
        background-color: darkred;
        border: 0;
        padding: 8px;
        font-size: 18px;
        text-align: center;
      }

      input:hover{
        padding: 20px;
        outline: 3px solid white;
      }

      button{
        border: 0;
        width: 15%;
        background-color: darkred;
        color: white;
        border-radius: 8px;
        padding: 8px;
        font-size: 18px;

      }

      button:hover{
        padding: 20px;
        outline: 3px solid white;
        font-size: 22px;
        font-weight: bolder;
      }
    }

  }




</style>
