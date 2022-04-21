<script>
import axios from "axios";
export default {
  data: function () {
    return {
      products: [],
    };
  },
  created: function () {
    this.indexProducts();
  },
  methods: {
    indexProducts: function () {
      axios.get("/products").then((response) => {
        console.log("products index", response);
        this.products = response.data;
      });
    },
  },
};
</script>

<template>
  <div class="products-index">
    <h1>All Products</h1>
    <div v-for="product in products" v-bind:key="product.name">
      <p>{{ product.name }}</p>
    </div>
    <!-- {{ product.name }} -->
  </div>
</template>
