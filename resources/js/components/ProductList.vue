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
        <ProductItem
          v-for="product in products"
          :key="product.id"
          :product="product"
          @add-to-cart-pi="addToCartPl"
        />
      </tbody>
    </table>
  </div>
</template>

<script>
import ProductItem from './ProductItem.vue';

export default {
  name: 'ProductList',
  components: {
    ProductItem
  },
  props: {
    products: {
      type: Array,
      required: true
    }
  },
  methods: {
    addToCartPl(product) {
      console.log('This is from ProductList', product);
      this.$emit('add-to-cart-pl', product);
    }
  }
};
</script>
