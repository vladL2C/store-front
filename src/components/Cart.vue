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

    </div>
    ( 0 )
  </div>
</template>

<script>
export default {};
</script>

<style>
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
  text-transform: capitalize;
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
