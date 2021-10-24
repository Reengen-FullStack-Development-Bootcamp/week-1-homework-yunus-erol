<template>
  <div id="app">
    <Header :basket="basket" />
    <div class="container-fluid d-flex justify-content-around flex-wrap align-items-center" >
      <div class="card_main" v-for="(item,i)  in logitems " :info="item" @addProduct="addProduct"
      :key="i" >

        <Product class="card__item" 
        :name="item.name" 
        :category="item.category" 
        :price="item.price" 
        :summary="item.summary" 
        :color="item.color" 
        :img="item.img"
        />

      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Product from './components/Product.vue'
import items from './components/items'

export default {
  name: 'App',
  components: {
    Header,
    Product,
  },
 
  data () {
    return {
        logitems: items,
        basket: []
      }
  },
   methods :{
     addProduct(e) {
       
      console.log(this.basket)
      console.log(e)

    }
  },
}
</script>

<style >
.container{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;

}
.card_main{
  margin-top: 50px;
  box-sizing: border-box;
  box-shadow: 1px 1px 5px slategray;
  border-radius: 10px;
 }

</style>>


