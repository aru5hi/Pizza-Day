<template>
  <div>
    <SideMenu :display="displayMenu"/>
    <nav>
      <ul>
        <li>
          <div :class="sideMenuClass" @click="sideMenuIconChange">
            <div class="bar1"></div>
            <div class="bar2"></div>
            <div class="bar3"></div>
          </div>
        </li>
        <li>
          <router-link class="nav-item brand" to="/">
            PizzaDay
          </router-link>
        </li>
        <li>
          <router-link class="nav-item right" to="/">
            <i class="fas fa-shopping-cart"></i>
          </router-link>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
import SideMenu from "@/components/SideMenu.vue"
export default {
  name: 'NavBar',
  data(){
    return{
      sideMenuClass:['side-menu'],
      displayMenu:false
    }
  },
  components:{
    SideMenu
  },
  methods:{
    sideMenuIconChange(){
      if(this.sideMenuClass.includes("change")) {   
        let index=this.sideMenuClass.indexOf("change");
        this.sideMenuClass.splice(index,1);
        this.displayMenu=false;
        }
      else{
        this.sideMenuClass.push("change");
        this.displayMenu=true;
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@font-face {
    font-family: "TheHouls";
    src:url("~@/assets/Fonts/the-houls.ttf");
  }
@font-face {
  font-family: "Raphtalia";
  src: url("~@/assets/Fonts/Raphtalia.otf"),
       url("~@/assets/Fonts/Raphtalia.ttf");
  }


ul li{
  display:inline-block;
  cursor:pointer;
}
 ul li .nav-item{
  text-decoration:none;
  color:white;
 }
 .side-menu{
   position:absolute;
   top:65px;
   left:70px;
   cursor:pointer;
   z-index:2;
 }
 .bar1 , .bar2, .bar3 {
  width: 35px;
  height: 4px;
  background-color: white;
  margin: 7px 0;
  transition: 0.4s;
}

.change .bar1 {
  -webkit-transform: rotate(-45deg) translate(-9px, 6px);
  transform: rotate(-45deg) translate(-9px, 6px);
}
.change .bar2 {opacity: 0;}
.change .bar3 {
  -webkit-transform: rotate(45deg) translate(-8px, -8px);
  transform: rotate(45deg) translate(-8px, -8px);
}

 .brand{
  position:absolute;
  font-size:80px;
  font-family:"Raphtalia";
  left:200px;
  top:20px;
   z-index:2;

 }
 .right{
   position:absolute;
   right:80px; 
   top:50px;
 }
  .fas{
    font-size:30px;
  }
</style>
