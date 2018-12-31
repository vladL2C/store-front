<template>
  <div id="app">
    <div class="container">
      <Header></Header>
      <div class="row">
        <div class="offset-sm-2 col-sm-4 col-12">
          <img
            id="classic-tee"
            src="./assets/images/classic-tee.webp"
            alt=""
            width="394"
            height="604"
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";

export default {
  name: "app",
  components: {
    Header
  }
};
</script>

<style>
#classic-tee {
  max-width: 100%;
  height: auto;
}
</style>
