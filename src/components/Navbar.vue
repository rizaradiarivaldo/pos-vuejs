<template>
  <b-row class="navbar">
    <b-col lg="1" md="1" cols="2">
      <img
        src="../assets/icon/list-black-48dp.svg"
        alt=""
        v-b-tooltip.hover
        title="Menu"
      />
    </b-col>
    <b-col lg="10" md="10" cols="8" class="mt-2">
      <h3><strong>Food Items</strong></h3>
    </b-col>
    <b-col lg="1" md="1" cols="2">
      <img
        src="../assets/icon/search.svg"
        alt=""
        v-b-tooltip.hover
        title="Search"
        v-b-toggle="'collapse-2'"
      />
    </b-col>
  </b-row>
</template>

<style scoped>
.navbar {
  background: #ffffff;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.25);
  padding-left: 0px;
  padding-right: 0px;
  padding-top: 15px;
  padding-bottom: 15px;
}

.navbar img {
  cursor: pointer;
}
</style>
