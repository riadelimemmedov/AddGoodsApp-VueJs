<template>
    <div v-if="productList.length > 0">
        <h3 class="text-center">Eklenen Ürünlerin Listesi</h3>
      <hr>
      <div class="row product-container">
        <products v-for='product in productList'>
            <img class="card-img-top" :src="product.selectedImage" :alt="product.title">
            <div class="card-body">
              <h5 class="card-title">{{product.title}}</h5>
              <small>
                <strong>Adet : </strong> {{product.count}}
              </small>
              <br>
              <small>
                <strong>Fiyat : </strong> {{product.price}}
              </small>
              <br>
              <small>
                <strong>Tutar : </strong> {{product.totalPrice}}
              </small>
            </div>
        </products>
      </div>
    </div>
</template>

<script>
  import {eventBus} from '../main.js'
  import Products from './Product.vue'

  export default{
    components:{
      'products':Products
    },
    data:function(){
      return{
        productList:[],
      }
    },
    created(){
      eventBus.$on('addedProductData',(product)=>{
        if(this.productList.length <= 5){
          this.productList.push(product)
          eventBus.$emit('progressBarUpdatedValue',this.productList.length)
        }
        else{
          alert('Daha fazla urun eklemeyessiniz')
        }
      })
    }
  }
</script>

<style scoped>

</style>
