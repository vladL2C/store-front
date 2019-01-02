<template>
  <div class="my-cart">
    <span class="crt-title">My Cart</span>
    <span class="cart-img">
      <img
        class="cart-img"
        src="../assets/images/cart.png"
        width="20"
        height="20"
        alt=""
      >
    </span>
    <div class="cart-items">
      <div
        class="item"
        v-for="(item, i) in items"
        :key="
        i"
      >
        <img
          src="../assets/images/classic-tee.webp"
          alt=""
          width="80"
          height="130"
          class="cart-item-img"
        >

        <div class="cart-details-container">
          <div> {{item.productName}}</div>
          <div> {{item.quantity}} x <span>
              <b>{{item.price}}</b>
            </span></div>
          <div> Size: {{item.size}}</div>
        </div>

        <div></div>
      </div>

    </div>
    ( {{quantity}} )
  </div>
</template>

<script>
import { EventBus } from "../event-bus.js";
export default {
  data() {
    return {
      cartDetails: {}
    };
  },
  computed: {
    quantity() {
      if (!this.cartDetails.productQuantity) return 0;
      return this.cartDetails.productQuantity;
    },
    items() {
      return this.cartDetails.cartItems;
    }
  },
  created(e) {
    EventBus.$on("cart-details", cartDetails => {
      this.cartDetails = cartDetails;
    });
  }
};
</script>

<style>
.cart-details-container div {
  margin-top: 10px;
}
.cart-details-container {
  display: inline-block;
  text-align: left;
  position: relative;
  bottom: 10px;
  margin-left: 10px;
}
.cart-item-img {
  clear: both;
  margin-left: 20px;
  margin-bottom: 20px;
}

.my-cart {
  float: right;
  padding: 6px;
  z-index: 5;
  cursor: default;
  border: 1.2px solid #f6f6f7;
  border-bottom: 1px solid white;
  font-size: 13px;
  font-weight: 600;
  color: #888888;
  height: 31px;
  width: 95px;
}

.my-cart:hover {
  color: #222222;
  background-color: white;
  border: 1.2px solid #cccccc;
  border-bottom: 1.2px solid white;
}

.my-cart:hover > .cart-items {
  display: block;
}

.cart-items {
  position: absolute;
  border: 1.2px solid #cccccc;
  width: 320px;
  min-height: 50px;
  right: 15px;
  top: 42px;
  border-top: none;
  display: none;
  transition: all 0.2s;
  z-index: 5;
  background-color: white;
}

.cart-items:before {
  content: "";
  display: block;
  margin: 1 auto;
  width: 70.5%;
  padding-top: 20px;
  border-top: 1.2px solid #cccccc;
  box-sizing: border-box;
}
</style>
