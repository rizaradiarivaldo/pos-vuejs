<template>
  <div class="main-sidebar">
    <b-row class="barisan">
      <b-col md="12">
        <img
          src="../assets/icon/shopping_cart-black-48dp.svg"
          alt=""
          v-b-toggle.my-cart
          v-b-tooltip.hover
          title="Cart"
          class="toCart"
        />
        <router-link to="/" v-b-tooltip.hover title="Food Items">
          <img src="../assets/icon/restaurant-black-48dp.svg" alt="" />
        </router-link>
        <router-link to="/about" v-b-tooltip.hover title="Dashboard">
          <img src="../assets/icon/assignment-black-48dp.svg" alt="" />
        </router-link>
        <router-link
          to=""
          v-b-tooltip.hover
          title="Add Product"
          v-b-modal.modal-1
        >
          <img src="../assets/icon/add.svg" alt="" />
        </router-link>
      </b-col>

      <b-sidebar id="my-cart" shadow width="100%">
        <div class="px-3 py-2">
          <Cart/>
        </div>
      </b-sidebar>
    </b-row>
  </div>
</template>

<style scoped>

.toCart {
  display: none;
}
@media (min-width: 768px) {
  .main-sidebar {
    width: 70px;
  }
  /* .barisan {
    right: 0 !important;
  }*/
}
@media (max-width: 768px) {
  .toCart {
    display: unset;
  }
  img {
    padding: 10px 8px;
    margin-top: -10px !important;
    margin-left: 10px;
    margin-right: 10px;
  }
}

img {
  margin-top: 40px;
}
</style>

<script>
import Cart from '../components/Cart'
export default {
  name: 'Sidebar',
  components: {
    Cart
  }
}
</script>
