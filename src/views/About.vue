<template>
  <div>
   <div class="container-fluid">
     <div class="row">
       <div class="col-lg-1">
        <img src="../assets/icon/list-black-48dp.svg" alt="">
       </div>
       <div class="col-lg-11">
          <h3><strong>Food Items</strong></h3>
       </div>
     </div>
     <div class="row">
       <div class="col-lg-1 col-md-1 col-12">
         <div class="row">
          <div class="col-lg-12 sidebar">
            <router-link to="/"><img src="../assets/icon/restaurant-black-48dp.svg" alt=""></router-link>
            <img src="../assets/icon/assignment-black-48dp.svg" alt="">
            <img src="../assets/icon/add.svg" alt="">
          </div>
        </div>
       </div>
        <div class="col-lg-11">
          <div class="row">
                <div class="col-md-12 col-12">
                  <div class="row text-center main-history">
                    <div class="col-md-4 col-12">
                      <div class="card-dashboard-left">
                        <div class="card-body font-weight-bold">
                          <p class="card-text">Today’s Income</p>
                          <p>+2% Yesterday</p>
                          <p>Rp. 1.000.000</p>
                        </div>
                      </div>
                    </div>
                    <div class="col-md-4 col-12">
                      <div class="card-dashboard-mid">
                        <div class="card-body font-weight-bold">
                          <p class="card-text">Orders</p>
                          <p>3.270</p>
                          <p>+5% Last Week</p>
                        </div>
                      </div>
                    </div>
                    <div class="col-md-4 col-12">
                      <div class="card-dashboard-right">
                        <div class="card-body font-weight-bold">
                          <p class="card-text">This Year’s Income</p>
                          <p>Rp. 100.000.000.000</p>
                          <p>+10% Last Year</p>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
        </div>
     </div>

   </div>
  </div>
</template>

<script>
// import NavHistory from '../components/NavHistory'
// import Sidebar from '../components/Sidebar'
export default {
  name: 'About',
  components: {
    // NavHistory
    // Sidebar
  }
}
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
}
.sidebar {
  display: flex;
  flex-direction: column;
}

.sidebar img {
  margin-top: 30px !important;
}

.card-dashboard-left {
  background: linear-gradient(278.29deg, #FBB2B4 30.05%, rgba(255, 143, 178, 0) 133.19%);
  filter: drop-shadow(10px 15px 10px rgba(255, 143, 178, 0.25));
  border-radius: 10px;
  margin: 30px;
  height: 100px;
}
.card-dashboard-mid {
  background: linear-gradient(278.29deg, #FBB2B4 30.05%, rgba(255, 143, 178, 0) 133.19%);
  filter: drop-shadow(10px 15px 10px rgba(255, 143, 178, 0.25));
  border-radius: 10px;
   margin: 30px;
  height: 100px;
}
.card-dashboard-right {
    background: linear-gradient(278.29deg, #FBB2B4 30.05%, rgba(255, 143, 178, 0) 133.19%);
  filter: drop-shadow(10px 15px 10px rgba(255, 143, 178, 0.25));
  border-radius: 10px;
 margin: 30px;
  height: 100px;
}
</style>
