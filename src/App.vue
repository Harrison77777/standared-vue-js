<template>
  <div id="app">
   <Navbar @searchResult="searchItems"></Navbar>
    <div class="invantory-and-cart-section mt-1">
      <div class="container">
        <div class="row">
          <CardSection @addedNewItem="addCartItem" :items="items"></CardSection>
          <CartSection :items="carts"></CartSection>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
import CardSection from './components/CardSection'
import CartSection from './components/CartSection'
import Navbar from './components/Navbar'
import data from './data.js'
import axios from 'axios'
  export default {
    components: {
    CardSection,
    CartSection,
    Navbar
    },
     data(){
      return {
        items: [],
        carts: []
        
      }
    },
    mounted(){
      this.items = data
      
    },
    methods:{
      addCartItem(item){
        this.carts.push(item)
      },
      searchItems(keyword){
        if (keyword == '') {
          this.items = data
        }else{
          this.items = data.filter(item => {
          return item.name.toLowerCase().indexOf(keyword.toLowerCase()) != -1
        })
        }
      },
     
     
    }
    
   
  };
</script>

<style>
</style>