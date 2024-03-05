<script>
import {store} from "../store";

export default{
    name:"AppSelect",

  data(){
    return{
      store,
    }
  },
  methods:{
    selectionChange(){
      store.archetypeSelected = document.querySelector("#card-select").value;
      console.log(store.archetypeSelected)
    }
  }
 
}

</script>

<template>

    <div id="select-box">
        <select @change="selectionChange(), $emit('changeArchetype')" id="card-select">
          <option v-for="currentArchetype in store.archetype" :value="currentArchetype.archetype_name">{{currentArchetype.archetype_name}}</option>
        </select>
    </div>
  
</template>

<style lang="scss">

@use '/src/styles/variables.scss' as *;
@use '/src/styles/mixins.scss' as *;


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
</style>
