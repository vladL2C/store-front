<template>
  <div class="offset-lg-1 col-lg-5 col-sm-12 col-12 col-md-12">
    <h4 class="product-title">Classic Tee</h4>
    <h6 class="product-price"> $75.00 </h6>
    <p class="product-description">
      Lorem ipsum dolor sit amet,
      consectetur adipiscing elit. Suspendisse ac aliquam dui.
      Donec commodo mattis metus ut euismod. Curabitur gravida
      dignissim nibh, nec volutpat enim feugiat sit amet. Morbi
      lectus urna, gravida in mi et, sodales dictum purus. Proin rhoncus ipsum vel
      euismod ullamcorper.
    </p>
    <div class="size-container">
      <span class="req-size">size</span>
      <span class="selected-size">{{selectedSize}}</span>
      <div class="store-buttons">
        <input
          type="radio"
          id="s"
          value="S"
          v-model="selectedSize"
        >
        <label for="s">S</label>

        <input
          type="radio"
          id="m"
          value="M"
          v-model="selectedSize"
        >
        <label for="m">M</label>

        <input
          type="radio"
          id="l"
          value="L"
          v-model="selectedSize"
        >
        <label for="l">L</label>
      </div>
    </div>
    <div
      @click="addItem"
      class="add-to-cart"
    >add to cart</div>
  </div>
</template>

<script>
import { EventBus } from "../event-bus.js";
export default {
  data() {
    return {
      cartItems: [],
      selectedSize: "",
      productQuantity: 0
    };
  },
  methods: {
    addItem() {
      if (!this.selectedSize) {
        alert("No Size selected");
        return;
      }
      const item = {
        productName: "Classic Tee",
        quantity: 1,
        size: this.selectedSize,
        price: "$75.00"
      };

      this.updateCart(item);
      EventBus.$emit("cart-details", {
        cartItems: this.cartItems,
        productQuantity: this.productQuantity
      });
    },
    updateCart(newItem) {
      for (let i = 0; i < this.cartItems.length; i++) {
        if (newItem.size == this.cartItems[i].size) {
          this.cartItems[i].quantity++;
          this.productQuantity++;
          return;
        }
      }

      this.cartItems.push(newItem);
      this.productQuantity++;
    }
  }
};
</script>

<style>
.selected-size {
  font-weight: bold;
  margin-left: 3px;
  font-size: 11px;
}
</style>
