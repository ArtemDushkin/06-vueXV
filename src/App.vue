
<template> 

<div class="block">
  <img src="./images/logo.jpg" style="width: 500px; height: 500px; align-items:center;">
 </div>
 <hr>
 <Info/>
 <hr>
 <div class="cart">Cart({{ cart }})</div>
 <h1>Выберите десерт по вкусу:</h1>
 <DesertType @add-to-cart="updateCart" @delete-from-cart="deleteCart"></DesertType>
 <hr>
 <h1>Выберите вкус/начинку</h1>
</template>

<script>
import Info from './components/info.vue' 
import DesertType from './components/desertType/desertType.vue'

export default {
  name: 'app',
  data() {
    return {
      cart: [],
      }
  },
  components: {
    Info,
    DesertType,
  },
  methods: {
    updateCart(type){
      this.cart.push(type);
    } , 
    deleteCart(){
      this.cart.length=0;
    }  
  }
}
</script>



<style scoped>
.cart {
  margin: 25px 100px;
  float: right;
  border: 1px solid #d8d8d8;
  padding: 30px 30px;
  background-color: white;
  -webkit-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
  -moz-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
  box-shadow: 2px 15px -12px rgba(0, 0, 0, 0.57);
}</style>
