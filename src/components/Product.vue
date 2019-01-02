<template>
  <div class="row">
    <div class="offset-lg-2 col-lg-4 col-sm-12 col-12 col-md-12">
      <img
        id="classic-tee"
        src="../assets/images/classic-tee.webp"
        alt=""
        width="394"
        height="604"
      >
    </div>
    <Product-Control></Product-Control>
  </div>
</template>


<script>
import ProductControl from "./Product-Control.vue";

export default {
  components: {
    ProductControl
  }
};
</script>

<style>
#classic-tee {
  width: 100%;
  height: auto;
}
</style>
