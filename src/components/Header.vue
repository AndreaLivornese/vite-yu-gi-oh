<script>

export default{

    name:"Header",

  data(){
    return{

    }
  }

}

</script>

<template>
 

    <header>
        <img src="/public/img/Yugiohpng.png" id="logo-headder" alt="logo yu-gi-oh">
        <h1>Yu-Gi-Oh Api</h1>

    </header>


</template>

<style lang="scss">

header{
    display:flex;
    gap:10px;

    #logo-headder{
        width: 70px;
        height: 70px;
    }

    h1{
        color:black;
        font-size: 44px;
        font-weight: 400;
    }
}


</style>
