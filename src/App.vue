<template>
  <div id="app">
    <div class="container">
      <Header></Header>
      <Product></Product>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Product from "./components/Product.vue";

export default {
  name: "app",
  components: {
    Header,
    Product
  }
};
</script>

<style>
@media only screen and (max-width: 768px) {
  .product-price {
    border: none;
  }

  .crt-title {
    display: none;
  }

  .product-title {
    margin-top: 20px;
  }

  .add-to-cart {
    margin-bottom: 20px;
  }

  .cart-items:before {
    width: 70.6%;
  }
}

@media only screen and (min-width: 769px) {
  .cart-img {
    display: none;
  }
}

@media (max-width: 320px) {
  .cart-items {
    width: 90%;
  }
  .cart-items:before {
    width: 67.5%;
  }
}
</style>
 