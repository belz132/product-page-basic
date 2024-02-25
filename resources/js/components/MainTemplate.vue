<template>
    <div class="container mt-3">
      <div class="row">
        <div class="col-md-8">
          <!-- Slot for ProductList -->
          <slot name="product-list"></slot>
        </div>
        <div class="col-md-4">
          <!-- Slot for ShoppingCart -->
          <slot name="shopping-cart"></slot>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'MainTemplate',
  };
  </script>
  
  <style>
  /* We add some styling specific to the layout here */
  </style>
  