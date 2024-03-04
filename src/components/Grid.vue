<script>

export default{
    name:"grid",

  data(){
    return{

    }
  }

}

</script>

<template>

<div class="grid">

    <div id="top-grid">
        Found tot cards
    </div>

    <div class="inner-grid">

        

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
}

</style>
