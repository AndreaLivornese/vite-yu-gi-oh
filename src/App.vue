<script>
import Header from "./components/Header.vue";
import grid from "./components/Grid.vue";
import {store} from "../src/store";
import AppSelect from "./components/AppSelect.vue";

export default{

  components:{
    Header,
    grid,
    AppSelect,
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
      store.cardsNumber = rep.data.meta.current_rows;
      console.dir(store.cards);
    });

    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then(function(rep){
      
      store.archetype = rep.data;
      console.dir(store.archetype);
    });

  },
  methods:{
    
    filterForArchetype(){
      console.log(store.archetypeSelected);
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0' + "&archetype=" + store.archetypeSelected).then(function(rep){
      
      store.cards = rep.data.data;
      store.cardsNumber = rep.data.meta.current_rows;
      console.log(store.cardsNumber)
      console.log(rep)
    });

    }

  }

}

</script>

<template>

  <Header></Header>

  <main>

    <div class="container">

      <AppSelect @changeArchetype=" filterForArchetype() "></AppSelect>

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
  }


</style>
