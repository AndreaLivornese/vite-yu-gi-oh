<script>

export default{
    name:"cardItem",


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
        <img :src="card.card_images[0].image_url" alt="immagine della carta">
    </div>
    <div class="card-info">
        <div class="card-name">
            {{ card.name }}
        </div>
        <div class="card-type">
            {{ card.archetype }}
        </div>
    </div>
  
</div>
  
</template>

<style lang="scss">

@use '/src/styles/variables.scss' as *;
@use '/src/styles/mixins.scss' as *;

.card{
    width: calc(100% / 5 - 35px / 5 * 4);

    .card-image{

        img{
            display: block;
            width: 100%;
        }
    }


    .card-info{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        padding:25px 20px 0;
        background-color: $primary;
        min-height: 130px;


        .card-name{
            text-align: center;
            color:white;
            text-transform: uppercase;
            line-height: 1.5em;
            font-size:16px;
        }

        .card-type{
            text-align: center;
            font-size:20px
        }
    }
}


</style>
