<template>
    <div>
      <h2>Keranjang Belanja</h2>
      <table class="table">
        <thead>
          <tr>
            <th>Name</th>
            <th>Quantity</th>
            <th>Price</th>
            <th>Actions</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in cartItems" :key="item.id">
            <td>{{ item.name }}</td>
            <td>
              <button class="btn btn-secondary" @click="updateQuantity(item, -1)" :disabled="item.quantity <= 1">-</button>
              {{ item.quantity }}
              <button class="btn btn-secondary" @click="updateQuantity(item, 1)" :disabled="item.quantity >= item.stock">+</button>
            </td>
            <td>Rp. {{ item.price * item.quantity }}</td>
            <td><button class="btn btn-danger" @click="removeFromCart(item)">Delete</button></td>
          </tr>
        </tbody>
      </table>
      <div class="text-end">
        <h3>Total: Rp. {{ total }}</h3>
        <button class="btn btn-success" @click="checkout" :disabled="!cartItems.length">Checkout</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ShoppingCart',
    props: {
      cartItems: Array
    },
    computed: {
      total() {
        return this.cartItems.reduce((acc, item) => acc + (item.price * item.quantity), 0);
      }
    },
    methods: {
      updateQuantity(item, quantityChange) {
        this.$emit('update-cart-quantity', item, quantityChange);
      },
      removeFromCart(item) {
        this.$emit('remove-from-cart', item);
      },
      checkout() {
        this.$emit('checkout');
      }
    }
  };
  </script>
  