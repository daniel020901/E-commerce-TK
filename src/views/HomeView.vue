<template>
  <div class="home">
    <Navbar />
    <div class="container">
      <heroView />
      <div class="row mt-4">
        <div class="col">
          <h2>Best<strong>Foods</strong></h2>
        </div>
        <div class="col">
          <router-link to="/FoodsName" class="btn btn-success float-right"><b-icon-eye></b-icon-eye>Lihat Semua </router-link>
        </div>
      </div>


      <div class="row mb-4">
        <div class="col-md-4 mt-4 " v-for="product in products" :key="product.id">
         <CardProduct :product="product" />
        </div>
       
        
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from '@/components/Navbar.vue'
import heroView from '@/components/heroView.vue'
import  CardProduct from '@/components/CardProduct.vue'
import axios from 'axios';

export default {
  name: 'HomeView',
  components: {
    Navbar,
    heroView,
    CardProduct,
  },
  data() {
    return {
      products: [],
    };
  },
  methods: {
    setProduct(data) {
      this.products = data;
    }
  },
  mounted() {
    axios.get('https://demo9988597.mockable.io/best-products')
  .then((response) => this.setProduct(response.data))
  .catch((error) => console.log("Gagal",error))
  
  },
};
</script>
