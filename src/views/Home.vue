<template>
  <b-container fluid>
    <b-row>
      <b-col lg="9" md="12" cols="12">
        <Navbar />
        <b-row>
          <b-col lg="1" md="1" class="sidebar-container">
            <Sidebar class="sidebar" />
          </b-col>
          <b-col lg="11" md="11" class="content">
            <Card :Category="dataCategory" v-on:emitCart="addToCart()" />
          </b-col>
        </b-row>
      </b-col>

      <b-col lg="3" class="cartLg">
        <div>
          <Cart/>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import Navbar from '../components/Navbar'
import Sidebar from '../components/Sidebar'
import Card from '../components/Card'
import Cart from '../components/Cart'
import axios from 'axios'

export default {
  name: 'Home',
  components: {
    Navbar,
    Sidebar,
    Card,
    Cart
  },
  data () {
    return {
      dataCategory: null
    }
  },
  methods: {
    getCategory () {
      axios
        .get('http://localhost:3300/category/getall')
        .then(result => {
          this.dataCategory = result.data.data
          // console.log(this.dataCategory)
        })
        .catch(err => {
          console.log(err)
        })
    }
  },
  mounted () {
    this.getCategory()
  }
}
</script>

<style scoped>
.sidebar {
  background: #ffffff;
  box-shadow: 0px 4px 1px rgba(0, 0, 0, 0.25);
  /* height: 159vh; */
  height: 100%;
}
.cartLg {
  display: unset;
}
@media (max-width: 992px) {
  .cartLg {
    display: none;
  }
}
@media (min-width: 768px) {
  .sidebar {
    position: absolute;
    left: 0;
    z-index: 2;
  }
}
@media (max-width: 768px) {
  .main-sidebar {
    width: 100%;
    height: 100%;
  }
  .sidebar-container {
    padding: 0;
  }
}
.cart {
  background: #ffffff;
  box-shadow: 0px 4px 1px rgba(0, 0, 0, 0.25);
  padding-top: 10px;
  padding-bottom: 10px;
}
</style>
