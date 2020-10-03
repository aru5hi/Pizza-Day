<template>
    <div class="tray">
        <div class="size-selection">
            <div class="label">SELECT SIZE</div>
            <div class="button-tray">
                <div class="size-button">S</div>
                <div class="size-button">M</div>
                <div class="size-button">L</div>
            </div>
        </div>
        <div class="pizza-menu">
            <div class="option-circle">
                <div class="option" @click="setSelectedPizza(pizzaMenuList[0])">margherita</div>
                <div class="option" @click="setSelectedPizza(pizzaMenuList[1])">chicken</div>
                <div class="option" @click="setSelectedPizza(pizzaMenuList[2])">Indiana</div>
                <div class="option" @click="setSelectedPizza(pizzaMenuList[3])">Veggie</div>
                <div class="option" @click="setSelectedPizza(pizzaMenuList[4])">Mexican</div>
                <div class="option" @click="setSelectedPizza(pizzaMenuList[5])">Russian</div>
                <div class="option" @click="setSelectedPizza(pizzaMenuList[6])">Pepperoni</div>
            </div>
            <div class="pizza-image">
                <img :src="getImgUrl" id="dynamic-pizza-image" :alt="selectedPizza.alt"/>
            </div>
        </div>
    </div>
</template>

<script>
export default{
    name:'Tray',
    data(){
        return{
            selectedPizza:{},
            pizzaMenuList:[
                {
                    name:"Margherita",
                    url:"marghrita2-transparent.png",
                    alt:"Margherita Pizza",
                    desciption:"Lorem Ipsum Lorem Ipsum is simply dummy text of the printing and typesetting industry Lorem Ipsum has been the"
                },
                {
                    name:"Chicken",
                    url:"chicken-transparent.png",
                    alt:"Chicken Pizza",
                    desciption:"Lorem Ipsum Lorem Ipsum is simply dummy text of the printing and typesetting industry Lorem Ipsum has been the"
                },
                {
                    name:"Indiana",
                    url:"indiana-pizza-transparent.png",
                    alt:"Indiana Pizza",
                    desciption:"Lorem Ipsum Lorem Ipsum is simply dummy text of the printing and typesetting industry Lorem Ipsum has been the"
                },
                {
                    name:"Veggie",
                    url:"veggie-transparent.png",
                    alt:"Veggie Pizza",
                    desciption:"Lorem Ipsum Lorem Ipsum is simply dummy text of the printing and typesetting industry Lorem Ipsum has been the"
                },
                {
                    name:"Mexican",
                    url:"veggie-transparent.png",
                    alt:"Mexican Pizza",
                    desciption:"Lorem Ipsum Lorem Ipsum is simply dummy text of the printing and typesetting industry Lorem Ipsum has been the"
                },
                {
                    name:"Russian",
                    url:"veggie-transparent.png",
                    alt:"Russian Pizza",
                    desciption:"Lorem Ipsum Lorem Ipsum is simply dummy text of the printing and typesetting industry Lorem Ipsum has been the"
                },
                {
                    name:"Pepperoni",
                    url:"pepperoni-transparent.png",
                    alt:"Pepperoni Pizza",
                    desciption:"Lorem Ipsum Lorem Ipsum is simply dummy text of the printing and typesetting industry Lorem Ipsum has been the"
                }                

            ]
        }
    },
    mounted(){
        this.setSelectedPizza(this.selectedPizza[0]);
    },
    methods:{
        setSelectedPizza(pizza){
            console.log(pizza);
            this.selctedPizza.name=pizza.name;
            this.selctedPizza.url=pizza.url;
            this.selctedPizza.alt=pizza.alt;
            this.selctedPizza.description=pizza.description;
            console.log(this.selctedPizza);
        },
        getImgUrl(){
            return require('../assets/Images/Transparent/'+this.selectedPizza.url)
        }
    }
}
</script>

<style scoped>
    @font-face{
        font-family:"heightning";
        src:url("~@/assets/Fonts/X-Heighting.otf");
    }
    .tray{
        position:absolute;
        left:760px;
        top:150px;
        text-align:center;
        color:white;
    }
    .size-selection{
        position:relative;
        font-family:'heightning';
        font-size:2em;
    }
    .label{
        font-size:1em;
        color:white;
    }
    .button-tray>.size-button{
        display:inline-block;

    }
    .size-button{
        width:35px;
        height:35px;
        margin:5px 14px;
        padding:10px 8px 5px 8px;
        line-height:-20px;
        background:rgba(255,255,255,0.4);
        border:1px solid white;
        border-radius: 100px;
        font-size:20px;
        cursor:pointer;
    }
    .size-button:hover{
        background:rgba(255,255,255,0.6);
        color:grey;
    }
    .pizza-menu{
        margin-top:100px;
    }
    .option-circle>.option{
        margin-right:10px;
        border:1px solid white;
    }
    #dynamic-pizza-image{
        margin-top:60px;
        height:200px;
        width:200px;
    }
</style>