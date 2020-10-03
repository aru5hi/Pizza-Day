<template>
  <div id="app">
    <div id="nav">
      <NavBar/>
    </div>
    <router-view/>
    <img src="./assets/Images/Transparent/Chilli-2-transparent.png" class="chilli" alt="">
    <img src="./assets/Images/Transparent/Mint-Transparent.png" class="mint" alt="">
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue'
export default {
  components: {
    NavBar
  }
}
</script>

<style>
#app{
    overflow:hidden; 
}
  .chilli{
    position:absolute;
    right:72px;
    bottom:30px;
    height:337px;
    width:200px;
     transform: rotate(31deg);
  }
  .mint{
    position:absolute;
    left:-56.8px;
    bottom:100px;
    width:250px;
    height:258px;
    transform: rotate(197deg);
  }
</style>
