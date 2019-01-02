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
      <div
        class="store-buttons"
        @click="selectSize"
      >
        <div
          class="size-button"
          :class="{highlight: selectedSize == 'S'}"
        >S</div>
        <div
          class="size-button"
          :class="{highlight: selectedSize == 'M'}"
        >M</div>
        <div
          class="size-button"
          :class="{highlight: selectedSize == 'L'}"
        >L</div>
      </div>
    </div>
    <div
      @click="addItem"
      class="add-to-cart"
    >add to cart</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedSize: ""
    };
  },
  methods: {
    addItem() {},
    selectSize(e) {
      this.selectedSize = e.target.innerText;
    }
  }
};
</script>

<style>
.highlight {
  border: 2px solid black;
  color: black;
}

.selected-size {
  font-weight: bold;
  margin-left: 3px;
  font-size: 13px;
  line-height: 23px;
}
</style>
