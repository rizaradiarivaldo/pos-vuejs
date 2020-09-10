<template>
  <div>
    <b-row>
      <b-col md="12" class="cart">
        <h3 class="text-center">
          <img
            src="../assets/icon/shopping_cart-black-48dp.svg"
            alt=""
            v-b-tooltip.hover
            title="Cart"
          />
          <span></span>
        </h3>
      </b-col>
    </b-row>
    <b-row>
      <b-col lg="12">
        <img src="../assets/img/food-and-restaurant.png" alt="" />
        <div class="col-md-12 text-center">
          <p>Your cart is empty</p>
        </div>
        <div class="col-md-12 text-center">
          <p>Please add some items from the menu</p>
        </div>
      </b-col>
    </b-row>
    <div class="row">
      <div class="col-md-12 col-12">
        <div class="row">
          <div class="col-md-4 col-4 text-center">
            <img src="../assets/img/coffe-latte.png" class="img-fluid" alt="" />
          </div>
          <div class="col-md-8 col-8">
            <div class="row">
              <div class="col-md-12 col-12 text-left">
                <p><strong>Coffe Latte</strong></p>
              </div>
              <div class="col-md-6 col-6">
                <div
                  class="btn-group btn-group-sm"
                  role="group"
                  aria-label="Basic example"
                >
                  <button type="button" class="btn btn-outline-success">
                    -
                  </button>
                  <button type="button" class="btn btn-outline-success">
                    1
                  </button>
                  <button type="button" class="btn btn-outline-success">
                    +
                  </button>
                </div>
              </div>
              <div class="col-md-6 col-6">
                <p><strong>Rp. 15.000</strong></p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-md-12 col-12">
        <div class="row">
          <div class="col-md-4 col-4">
            <img src="../assets/img/blackforest.png" class="img-fluid" alt="" />
          </div>
          <div class="col-md-8 col-8">
            <div class="row">
              <div class="col-md-12 col-12">
                <p><strong>Black Forest</strong></p>
              </div>
              <div class="col-md-6 col-6">
                <div
                  class="btn-group btn-group-sm"
                  role="group"
                  aria-label="Basic example"
                >
                  <button type="button" class="btn btn-outline-success">
                    -
                  </button>
                  <button type="button" class="btn btn-outline-success">
                    1
                  </button>
                  <button type="button" class="btn btn-outline-success">
                    +
                  </button>
                </div>
              </div>
              <div class="col-md-6 col-6">
                <p><strong>Rp. 30.000</strong></p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-md-12 col-12">
        <div class="row">
          <div class="col-md-4 col-4">
            <img src="../assets/img/salmon.png" class="img-fluid" alt="" />
          </div>
          <div class="col-md-8 col-8">
            <div class="row">
              <div class="col-md-12 col-12">
                <p><strong>Salmon Truffle</strong></p>
              </div>
              <div class="col-md-6 col-6">
                <div
                  class="btn-group btn-group-sm"
                  role="group"
                  aria-label="Basic example"
                >
                  <button type="button" class="btn btn-outline-success">
                    -
                  </button>
                  <button type="button" class="btn btn-outline-success">
                    1
                  </button>
                  <button type="button" class="btn btn-outline-success">
                    +
                  </button>
                </div>
              </div>
              <div class="col-md-6 col-6">
                <p><strong>Rp. 60.000</strong></p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="row">
      <div class="col-md-12" style="margin-top: 100px">
        <div class="row">
          <div class="col-md-6 text-left">
            <strong>Total : </strong>
          </div>
          <div class="col-md-6 text-right">
            <strong>Rp. 105.000*</strong>
          </div>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-md-12 text-left" style="margin-bottom: 15px">
        *Belum termasuk ppn
      </div>
    </div>
    <div class="row">
      <div class="col-md-12 text-center">
        <button
          class="btn btn-block btn-checkout text-center"
          v-b-modal.modal-3
        >
          <strong>Checkout</strong>
        </button>

        <button class="btn btn-block btn-cancel text-center">
          <strong>Cancel</strong>
        </button>
      </div>
    </div>
    <b-modal id="modal-3" hide-header hide-footer>
      <div class="modal-body font-weight-bold">
        <div class="row">
          <div class="col-6">Checkout</div>
          <div class="col-6 text-right">Receipt no: #010410919</div>
        </div>
        <div class="row">
          <div class="col-6">Cashier : Pevita Pearce</div>
        </div>
        <br />
        <br />
        <div class="row">
          <div class="col-6 mb-3">Coffe Latte 1x</div>
          <div class="col-6 text-right">Rp. 15.000</div>
        </div>
        <div class="row">
          <div class="col-6 mb-3">Black Forest 1x</div>
          <div class="col-6 text-right">Rp. 30.000</div>
        </div>
        <div class="row">
          <div class="col-6 mb-3">Salmon Truffle Teriyaki 1x</div>
          <div class="col-6 text-right">Rp. 60.000</div>
        </div>
        <div class="row">
          <div class="col-6 mb-4">Ppn 10 %</div>
          <div class="col-6 text-right">Rp. 10.500</div>
        </div>
        <div class="row">
          <div class="col-6"></div>
          <div class="col-6 text-right">Total: Rp. 115.500</div>
        </div>
        <div class="row">
          <div class="col-12 mb-3">Payment: Cash</div>
        </div>
        <button
          type="button"
          style="background: #f24f8a; color: #ffffff; font-size: 20px"
          class="btn btn-block mb-1"
        >
          <strong>Print</strong>
        </button>
        <h5 class="text-center"><strong>Or</strong></h5>
        <button
          type="button"
          style="background: #57cad5; color: #ffffff; font-size: 20px"
          class="btn btn-block"
        >
          Send Email
        </button>
      </div>
    </b-modal>
  </div>
</template>

<style scoped>
.cart {
  background: #ffffff;
  box-shadow: 0px 4px 1px rgba(0, 0, 0, 0.25);
  padding-top: 10px;
  padding-bottom: 10px;
}

.btn-checkout {
  background: #57cad5;
  color: white;
}
.btn-checkout:hover {
  color: white !important;
  background: #3ad9e7;
}

.btn-cancel {
  background: #f24f8a;
  color: white;
}
.btn-cancel:hover {
  color: white !important;
  background: #c03d6d;
}
</style>
