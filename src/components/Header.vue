<template>
  <div class="row">
    <div class="header"></div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  width: 100%;
  height: 30px;
  background-color: #f6f6f7;
  margin-top: 12px;
  margin-bottom: 30px;
}
</style>
