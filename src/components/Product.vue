<template>
  <div class="main-card">
    <div class="product">
        <div class="images">
            <img v-bind:src="require('../assets/' + img)" />
        </div>
        <div class="choose-size"> 

            <p :class="this.color">CHOOSE SIZE</p>

            <div class="sizes" >

                <div @click="selectedSize" class="size" :class="`border-color-${this.color} ${this.color} size-${this.color}`">38</div>
                <div @click="selectedSize" class="size" :class="`border-color-${this.color} ${this.color} size-${this.color}`">39</div>
                <div @click="selectedSize" class="size" :class="`border-color-${this.color} ${this.color} size-${this.color}`">40</div>
                <div @click="selectedSize" class="size" :class="`border-color-${this.color} ${this.color} size-${this.color}`">41</div>
                <div @click="selectedSize" class="size" :class="`border-color-${this.color} ${this.color} size-${this.color}`">42</div>
                <div @click="selectedSize" class="size" :class="`border-color-${this.color} ${this.color} size-${this.color}`">43</div>
                <div @click="selectedSize" class="size" :class="`border-color-${this.color} ${this.color} size-${this.color}`">44</div>
                <div @click="selectedSize" class="size" :class="`border-color-${this.color} ${this.color} size-${this.color}`">45</div>
            </div>
            </div>
    </div>
    <div class="summary">

        <p class="head" 
        :class="this.color">{{ category }}
        </p>

        <h1 class="main">{{ name }}</h1>

        <h2 
        :class="this.color">${{ price }}
        </h2>

        <Rating :color="color" :star="star"/>

        <p class="desc">{{ summary }} </p>

        <div class="buttons" >

            <div class="select-value">
                <select  
                :class= "this.color"  
                name="value" 
                id="value">

                    <option value="1">1</option>
                    <option value="2">2</option>
                    <option value="3">3</option>
                    <option value="4">4</option>
                    <option value="5">5</option>
                    <option value="6">6</option>
                    <option value="7">7</option>
                    <option value="8">8</option>
                    <option value="9">9</option>
                    <option value="10">10</option>

                </select>
            </div>
            <button @click="addToBasket(info)" class="add white" 
            :class="`bg-${this.color}`" >Add to Cart</button>

        </div>
    </div>
  </div>
</template>


<script>
import Rating from './Rating.vue'


export default {
  name: 'Product',
  props: {
  name: String,
  category: String,
  summary:String,
  color:String,
  price:Number,
  star:Number,
  img:String,
  info:Object,
  basket:Array
  },
  data(){
      return {
          setSize : null,
       }
  },
  components: {
    Rating,
  },
  computed: {},
  methods: {
      selectedSize(e){
        const sizes = document.querySelectorAll(`.focus`)
        sizes.forEach(element => {
            element.classList.remove("focus");
            })
        e.target.classList.add("focus");
        this.setSize = e.target.innerText
        this.price = this.setSize * 5
      },
      addToBasket(val) {
       this.$emit('addProduct', val);

  }
  }
       
    
}

</script>

<style>

.focus{
    background-color:#90fde2;
    color: #F5F5F5;
}
.pink{
    color:#C3A1A0;
}
.blue{
    color:#7ccde6;
}
.bg-pink{
    background-color:#C3A1A0;
}
.bg-blue{
    background-color:#7ccde6;
}
.white{
    color: #F5F5F5;
}

.buttons{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.select-value{
    border: hidden;
    font-size: 14px;


}
select:focus{
outline: none;
}
select{
    border: hidden;
    font-size: 14px;
    width: 50px;
    padding: 7px;
    margin-right: 5px;
}
select-items{
    border: hidden;
    font-size: 14px;
}
button{
    border: none;
    padding: 5px;
    display: inline-block;
    outline: 0;
    margin: -1px;
    border-radius: 2px;
    text-transform: uppercase;
    letter-spacing: 1px;
    cursor: pointer;
}
.main-card{
    box-sizing: border-box;
    width: 520px;
    height: 350px;
    padding: 10px;
    border-radius: 10px;
    display: flex;
    justify-content: space-between;
    background-color: #f6f4f5;
    padding: 20px;
}
.product{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    

    
}
.summary{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    margin-left: 10px;
}
.choose-size{
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    margin-top: 11px;
    margin-bottom:0;
    margin-left: 20px;
}
.choose-size p{
    margin-bottom: 1px;
    font-size: .7rem;

}
.sizes{
    display: flex;

}
.border-color-pink{
    border: 1px solid #E0C9CB;
}
.border-color-blue{
    border: 1px solid #7ccde6;
}
.size{
    text-align: center;
    padding: 9px;

    font-size: 0.7em;
    margin-right: 3px;
}
.size-pink:hover{
    background-color:#C3A1A0;
    color: #F5F5F5;
}
.size-blue:hover{
    background-color:#7ccde6;
    color: #F5F5F5;
}

img {
  width: 300px;
}
.head{
    font-size: 14px;
    margin-top:-5px ;
}
.main {
  font-size: 1.2em;
  margin-top: -15px;
 
}
.desc{
    font-size: .7em;
}
.add{
    width: 100%;
}
</style>