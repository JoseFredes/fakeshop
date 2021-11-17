<template>
  <v-row>
    <v-col v-for="product in products" :key="product.id" cols="4">
      <v-card :loading="loading" class="mx-auto my-12" max-width="374">
        <v-card-title class="card-title"
          ><h5>{{ product.title }}</h5></v-card-title
        >
        <v-card-actions><v-img :src = "product.image"></v-img></v-card-actions>
        <br />
        <v-card-subtitle class="card-subtitle">{{
          product.category
        }}</v-card-subtitle>

        <v-card-text>{{ product.description }}</v-card-text>
        <v-card-text class="card-price"
          >Price : {{ product.price }}</v-card-text
        >
        <v-btn block color="#7B1FA2" @click="drawer = !drawer"
          >Add To Cart</v-btn
        >
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import Vue from 'vue'
import Vuex from 'vuex'

Vue.use(Vuex)
export default {
  
  data() {
    return {
      products: [],
      data: () => ({ drawer: null }),
      
    }
    
  },
  async fetch() {
    // this.products = await this.$http.$get('https://fakestoreapi.com/products')
    const res = await fetch('https://fakestoreapi.com/products')
    this.products = await res.json()
    
  },
  
  
}
</script>

<style>
* {
  color: whitesmoke;
}
.card-title {
  text-align: center;
}
.card-price {
  text-align: center;
}
</style>
