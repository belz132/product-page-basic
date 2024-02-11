<template>
    <div>
      <h2>Semua Produk</h2>
      <table class="table">
        <thead>
          <tr>
            <th>Name</th>
            <th>Description</th>
            <th>Stock</th>
            <th>Price</th>
            <th>Action</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="product in products" :key="product.id">
            <td>{{ product.name }}</td>
            <td>{{ product.description }}</td>
            <td>{{ product.stock }}</td>
            <td>Rp. {{ product.price }}</td>
            <td>
              <button class="btn btn-primary" @click="addToCart(product)" :disabled="product.stock <= 0">Add to cart</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ProductList',
    props: {
      products: Array
    },
    methods: {
      addToCart(product) {
        this.$emit('add-to-cart', product);
      }
    }
  };
  </script>
  