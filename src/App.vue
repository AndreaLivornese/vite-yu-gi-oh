<script>
import Header from "./components/Header.vue";
import grid from "./components/Grid.vue";
import {store} from "../src/store";

export default{

  components:{
    Header,
    grid,
  },

  data(){
    return{

      store,

    }
  },
  mounted(){
    // chiamata alla API
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(function(rep){
      
      store.cards = rep.data.data;
      console.dir(store.cards);
    });
  }

}

</script>

<template>

  <Header></Header>

  <main>

    <div class="container">

      <div id="select-box">
        <select id="card-select">
          <option value="allen">Allen</option>
        </select>
      </div>

      <grid></grid>

    </div>

  </main>
 
</template>

<style lang="scss">

@use '/src/styles/variables.scss' as *;
@use '/src/styles/mixins.scss' as *;

  main{
    background-color: $primary;

    .container{
      @include container;
    }

    #select-box{
      padding: 26px 18px;

      select{
        width: 140px;
        height: 35px;

        border-radius: 8px;

        background-color: white;
        color:black;
      }
    }
  }


</style>
