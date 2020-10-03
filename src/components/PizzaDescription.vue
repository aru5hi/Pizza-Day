<template>
<div class="des">
    <div class="description">
        <div class="pizza-title">
            {{pizza.title}}
        </div>
        <div class="pizza-description">
            {{pizza.description}}
        </div>
    </div>
    <div>
        <span class="price-label">
            PRICE
        </span>
        <span class="price">
          <b>₹</b> {{pizza.price}} 
        </span>
    </div>
</div>
</template>

<script>
    export default{
        name:'PizzaDescription',
        data(){
            return{
                pizza:
                    {
                        name:"margherita",
                        title:"Margherita",
                        description:"Lorem Ipsum Lorem Ipsum is simply dummy text of the printing and typesetting industry Lorem Ipsum has been the",
                        price:328
                    }
            }
        }
    }
</script>

<style scoped>
    @font-face{
        font-family:"heightning";
        src:url("~@/assets/Fonts/X-Heighting.otf");
    }
    .description{
        position:absolute;
        left:110px;
        top:200px;
        color:white;
        width:250px;
    }
    .pizza-title{
        font-family:"heightning";
        font-size:40px;
    }
    .pizza-description{
        margin-top:20px;
        font-size:16px;
        font-family:"Helvetica";
        font-weight:bold;
    }
    .price-label{
        position:absolute;
        font-family:'Heightning';
        color:rgba(255,255,255,0.7);
        font-size:40px;
        right:200px;
        top:210px;
    }
    .price{
        position:absolute;
        font-family:'Heightning';
        color:white;
        font-size:35px;
        top:270px;
        right:210px;
    }
</style>