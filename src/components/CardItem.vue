<script>

export default{
    name:"card",


    props:{
        card:Object,
    },

  data(){
    return{

    }
  }

}

</script>

<template>

<div class="card">

    <div class="card-image">
        <img src="" alt="">
    </div>
    <div class="card-info">
        <div class="card-name">

        </div>
        <div class="card-type">
            
        </div>
    </div>
  
</div>
  
</template>

<style lang="scss">

@use '/src/styles/variables.scss' as *;
@use '/src/styles/mixins.scss' as *;

.card{
    width: calc(100% / 5 - 35px / 5 * 4);

    img{
        width: 100%;
    }

    .card-info{
        padding:35px 30px;


        .card-name{
            text-align: center;
            color:white;
            text-transform: uppercase;
            line-height: 1.5em;
            font-size:20px;
        }

        .card-type{
            font-size:24px
        }
    }
}


</style>
