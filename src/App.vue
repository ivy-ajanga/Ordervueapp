<template>
  <div id="nav">

            <router-link to ="/">Orders</router-link> |
            <router-link to ="/products">Products</router-link> |
            <router-link to ="/suppliers">Suppliers</router-link> |
            <router-link to ="/supplier_products">supplier_products</router-link> |
            <router-link to ="/order_details">order_details</router-link>
    <add-order></add-order>
    <router-view></router-view>
  </div>
</template>
<script>
  import Orders from './components/Orders.vue';
  /* import Products from './components/Products.vue';
  import supplier_products from './components/supplier_products.vue';
  import Suppliers from './components/Suppliers.vue';
  import order_details from './components/order_details.vue';*/
  /*import header from './components/header.vue';*/
  

  export default {
    name: 'app',
    components: { 
      'add-order': Orders,
      /*'app-header': header,*/
      /*'show-products': Products,
      'show-supplier_products': supplier_products,
      'show-order_details':order_details,
      'show-suppliers': Suppliers*/
    }
  }
</script>
<style>

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

}
#nav {
  padding: 30px;
  text-align:center ;

}
#nav a {
  font-weight: bold;
  color: #2c3e50;
  
}
#nav a.router-link-exact-active{
  color:#42b983;
 
}
</style>