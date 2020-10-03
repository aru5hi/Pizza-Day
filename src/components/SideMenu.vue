<template>
    <div >
        <nav :class="sideMenuBarClass">
            <ul>
            <li class="menu-item">
                Your Cart
            </li>
            <li class="menu-item">
                Account
            </li>
            </ul>
        </nav>
    </div>
</template>

<script>
export default {
  name: 'SideMenu',
  data(){
    return{
        sideMenuBarClass:["side-menu-bar","side-width-zero"]
    }
  },
  props:{
      display:{
          type:Boolean,
          default:false
      }
  },
  watch:{
      display:function(){
        if(this.display===true){
            this.sideMenuBarClass.push("side-width-full");   
        }
        else{
            let index=this.sideMenuBarClass.indexOf("side-width-full");
            this.sideMenuBarClass.splice(index,1);           
            this.sideMenuBarClass.push("side-width-zero");   
        }
    }
  }
}
</script>

<style scoped>
    .side-menu-bar{
        position: absolute;
        background:rgba(0,0,0,0.8);
        text-align:center;
        left:-5px;
        top:-5px;
        height:100%;
        z-index:2;
        transition: 0.5s;
        color:white;
        overflow-x: hidden;

    }
    ul{
        position:absolute;
        left:50px;
        top:150px;
        width:100%;
    }
    .menu-item{
        list-style-type:none;
        color:white;
        font-family:"TheHouls";
        font-size:30px;
        padding:15px;
        z-index:2;
    }

    .side-width-zero{
        width:0px;
    }

    .side-width-full{
       width:500px
    }
</style>