<script>
import cardItem from "./CardItem.vue"
import {store} from "../store";

export default{
    name:"grid",

    components:{
        cardItem,
    },

  data(){
    return{
        store,
    }
  }

}

</script>

<template>

<div class="grid">

    <div id="top-grid">
        Found tot cards
    </div>

    <div id="inner-grid">

        <cardItem v-for="currentCard in store.cards" :card="currentCard"></cardItem>

    </div>

</div>
  
</template>

<style lang="scss">

@use '/src/styles/variables.scss' as *;
@use '/src/styles/mixins.scss' as *;


.grid{
    padding:70px;

    background-color: white;


    #top-grid{
        padding:35px 25px;

        color:white;
        background-color: #212529;

        font-weight: bold;
        font-size:20px;
    }

    #inner-grid{
        display: flex;
        gap:35px;
        flex-flow: row wrap;
    }

}

</style>
