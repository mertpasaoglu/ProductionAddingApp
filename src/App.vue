<template>
  <div class="container">
    <h1 class="text-center">Ürün Ekleme Uygulaması</h1>
    <hr>
    <app-item-specs></app-item-specs>
    <br><br>
    <app-progress-bar></app-progress-bar>
    <br><br>
    <app-product></app-product>
  </div>


</template>

<script>

import itemSpecs from "../src/components/itemSpecs.vue";
import progressBar from "../src/components/progressBar.vue";
import product from "../src/components/product.vue";

  export default {
    components: {
     appItemSpecs : itemSpecs,
     appProgressBar : progressBar,
     appProduct : product,
   },
  }
</script>

<style>
  body {
    background-color: rgb(159, 159, 248);
    padding-top: 20px;
    padding-bottom: 20px;
    margin-top: 50px;
  }

  .card{
    margin-right: 5px;
    margin-bottom: 5px;
    background-color: rgb(230, 201, 250);
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

