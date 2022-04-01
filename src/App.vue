<template>
  <div class="container">
    <h1 class="text-center">Ürün Ekleme Uygulaması</h1>
    <hr>
    <!-- NewProduct Component -->
      <new-product-app></new-product-app>
    <!-- xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx -->
    <br><br>

    <!-- Progress App --->
    <progress-app></progress-app>
    <!-- xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx --->
    <br><br>



    <!-- App Products1 --->

    <app-products></app-products>
    <!-- xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx -->


  </div>


</template>

<script>
  import NewProduct from './components/NewProduct.vue'
  import Progress from './components/Progress.vue'
  import Products from './components/Products'

  export default {
    components:{
      'new-product-app':NewProduct,
      'progress-app':Progress,
      'app-products':Products,
    },
  }
</script>

<style>
  body {
    background-color: aliceblue;
    padding-top: 20px;
    padding-bottom: 20px;
  }

  .card{
    margin-right: 5px;
    margin-bottom: 5px;
  }

  .card:last-child{
    margin-right: 0px;
  }

  .col-md-2{
    max-width: 15.666667%!important;
  }

  .product-container{
    margin-left: 15px;
  }

</style>

