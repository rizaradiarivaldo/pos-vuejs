<template>
  <div>
    <b-row>
      <b-col lg="12">
        <b-collapse id="collapse-2">
          <b-card>
            <b-row class="my-1">
              <b-col sm="12">
                <b-form-input
                  @keyup="searchkey"
                  v-model="searchvalue"
                  id="input-small"
                  size="lg"
                  placeholder="Search..."
                ></b-form-input>
              </b-col>
            </b-row>
          </b-card>
        </b-collapse>
      </b-col>
    </b-row>
    <b-row>
      <b-col lg="12" md="12" cols="12" class="text-right mt-2 mb-2">
        <b-dropdown id="dropdown-1" text="Sort" class="m-md-2">
          <b-dropdown-item @click="sort('productname')"
            >By Name</b-dropdown-item
          >
          <b-dropdown-item @click="sort('price')">By Price</b-dropdown-item>
          <b-dropdown-item @click="sortLatest('desc')"
            >Latest Product</b-dropdown-item
          >
        </b-dropdown>
      </b-col>
    </b-row>
    <div>
      <b-row class="content-item">
        <b-col
          lg="4"
          md="4"
          cols="6"
          v-for="(item, index) in data"
          :key="index"
        >
          <div class="card-item">
            <img
              fluid
              class="card-img-top"
              :src="`http://localhost:3300/${item.image}`"
              alt="Expresso"
            />
            <div class="card-bottom">
              <p style="margin-bottom: -3px; text-align: left">
                {{ item.productname }}
              </p>
              <p style="text-align: left">
                <strong>Rp. {{ item.price }}</strong>
              </p>
              <div>
                <button class="btn btn-sm btn-primary">Add To Cart</button>
                <button class="btn btn-sm btn-success ml-1" v-b-modal.modal-update @click="update(item.id_product,index)">Update</button>
                <button class="btn btn-sm btn-danger ml-1" @click="deleteData(item.id_product)">delete</button>
              </div>
            </div>
          </div>
        </b-col>
        <b-modal id="modal-1" hide-header hide-footer>
          <div>
            <form @submit="sendData" enctype="multipart/form-data">
              <div class="row">
                <div class="col-sm-12">
                  <h4 class="text-left font-weight-bold mt-1 mb-4">Add Item</h4>
                </div>
              </div>
              <div class="form-group row">
                <label for="name" class="col-sm-2 col-form-label"
                  ><strong>Name</strong></label
                >
                <div class="col-sm-10">
                  <input type="text" class="form-control bg-input" id="name" v-model="productname" />
                </div>
              </div>

              <div class="form-group row">
                <label for="image" class="col-sm-2 col-form-label"
                  ><strong>Image</strong></label
                >
                <div class="col-sm-10">
                  <input
                    type="file" @change="process($event)"
                    class="form-control bg-input"
                    id="image"
                  />
                </div>
              </div>

              <div class="form-group row">
                <label for="price" class="col-sm-2 col-form-label"
                  ><strong>Price</strong></label
                >
                <div class="col-sm-10">
                  <input
                    type="text"
                    class="form-control  bg-input"
                    id="price" v-model="price"
                  />
                </div>
              </div>

              <div class="form-group row">
                <label for="category" class="col-sm-2 col-form-label"
                  ><strong>Category</strong></label
                >
                <div class="col-sm-10">
                  <select class="custom-select mr-sm-2  bg-input" id="category" v-model="id_category">
                    <option :value="null">Choose Category</option>
                    <option v-for="(item, index) in Category" :key="index" :value="item.id_category">{{ item.category }}</option>
                  </select>
                </div>
              </div>
                <div class="row">
                  <div class="col-sm-12 text-right" style="margin-top: 100px">
                    <button type="button" class="btn-cancel"><strong>Cancel</strong></button>
                    <button type="submit"  class="btn-add"><strong>Add</strong></button>
                  </div>
                </div>
            </form>
          </div>
        </b-modal>

          <b-modal id="modal-update" title="BootstrapVue" hide-header hide-footer>
             <div>
            <form @submit="updateData"  enctype="multipart/form-data">
              <div class="row">
                <div class="col-sm-12">
                  <h4 class="text-left font-weight-bold mt-1 mb-4">Edit Data</h4>
                </div>
              </div>
              <div class="form-group row">
                <label for="name" class="col-sm-2 col-form-label"
                  ><strong>Name</strong></label
                >
                <div class="col-sm-10">
                  <!-- :value="oldproductname" -->
                  <input type="text" class="form-control bg-input" id="name" v-model="oldproductname" />
                </div>
              </div>

              <div class="form-group row">
                <label for="image" class="col-sm-2 col-form-label"
                  ><strong>Image</strong></label
                >
                <div class="col-sm-10">
                  <input
                    type="file" @change="process($event)"
                    class="form-control bg-input"
                    id="image"
                  />
                </div>
              </div>

              <div class="form-group row">
                <label for="price" class="col-sm-2 col-form-label"
                  ><strong>Price</strong></label
                >
                <div class="col-sm-10">
                  <input
                    type="text"
                    class="form-control  bg-input"
                    id="price" v-model="oldprice"
                  />
                </div>
              </div>

              <div class="form-group row">
                <label for="category" class="col-sm-2 col-form-label"
                  ><strong>Category</strong></label
                >
                <div class="col-sm-10">
                  <select class="custom-select mr-sm-2  bg-input" id="category" v-model="id_category">
                    <option disabled :value="null">Choose Category</option>
                    <option v-for="(item, index) in Category" :key="index" :value="item.id_category">{{ item.category }}</option>
                  </select>
                </div>
              </div>
                <div class="row">
                  <div class="col-sm-12 text-right" style="margin-top: 100px">
                    <button type="reset" class="btn-cancel"><strong>Cancel</strong></button>
                    <button type="submit" class="btn-add"><strong>Add</strong></button>
                  </div>
                </div>
            </form>
          </div>
          </b-modal>
      </b-row>
    </div>
  </div>
</template>

<style scoped>
.card-item {
  padding: 10px 10px;
}
.bg-input {
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.25);
}
.btn-add {
  background: #57CAD5;
  color: white;
  text-decoration: none;
  border: none;
  margin-left: 15px;
  padding: 5px 10px;
  width: 100px;
  border-radius: 5px;
  height: 40px;
}
.btn-add:hover {
  background:  #14cbdb;
}

.btn-cancel {
  background: #F24F8A;
  color: white;
  text-decoration: none;
  border: none;
  margin-left: 15px;
  padding: 5px 10px;
  width: 100px;
  border-radius: 5px;
  height: 40px;
}

.btn-cancel:hover {
  background: #F24F8A;
}
</style>

<script>
import axios from 'axios'
export default {
  name: 'Card',
  props: ['Category'],
  data () {
    return {
      data: null,
      searchvalue: '',
      dataCategory: null,
      dataUpdate: [],

      productname: null,
      image: null,
      price: null,
      id_category: null,

      id_update: null,
      oldproductname: null,
      oldimage: null,
      oldprice: null,
      oldidcategory: null
    }
  },
  methods: {
    getAll () {
      axios
        .get('http://localhost:3300/product/getall')
        .then(result => {
          this.data = result.data.data
        })
        .catch(err => {
          console.log(err)
        })
    },
    searchkey () {
      axios
        .get(`http://localhost:3300/product/getall?name=${this.searchvalue}`)
        .then(result => {
          this.data = result.data.data
        })
        .catch(err => {
          console.log(err)
        })
    },
    sort (sortby) {
      axios
        .get(`http://localhost:3300/product/getall?sort=${sortby}`)
        .then(result => {
          this.data = result.data.data
        })
        .catch(err => {
          console.log(err)
        })
    },
    sortLatest (sortby) {
      axios
        .get(`http://localhost:3300/product/getall?typesort=${sortby}`)
        .then(result => {
          this.data = result.data.data
        })
        .catch(err => {
          console.log(err)
        })
    },
    getdetail (id) {
      axios.get(`http://localhost:3300/product/getdetail/${id}`)
        .then((result) => {
          this.dataUpdate = result.data.data
          console.log(result.data.data)
        }).catch((err) => {
          console.log(err)
        })
    },
    update (id, index) {
      this.id_update = id
      this.oldproductname = this.data[index].productname
      this.oldimage = this.data[index].image
      this.oldprice = this.data[index].price
      this.oldidcategory = this.data[index].id_category
    },
    updateData () {
      const fd = new FormData()
      fd.append('productname', this.oldproductname)
      fd.append('image', this.image)
      fd.append('price', this.oldprice)
      fd.append('id_category', this.id_category)

      console.log(this.oldproductname)
      console.log(this.image)
      console.log(this.oldprice)
      console.log(this.id_category)
      axios.put(`http://localhost:3300/product/update/${this.id_update}`, fd)
        .then((result) => {
          console.log(result)
        }).catch((err) => {
          console.log(err)
        })
    },
    deleteData (id) {
      axios.delete(`http://localhost:3300/product/delete/${id}`)
        .then((result) => {
          console.log(result)
        }).catch((err) => {
          console.log(err)
        })
      this.getAll()
    },
    // proccess
    process (event) {
      this.image = event.target.files[0]
    },
    sendData () {
      const fd = new FormData()
      fd.append('productname', this.productname)
      fd.append('image', this.image)
      fd.append('price', this.price)
      fd.append('id_category', this.id_category)

      axios.post('http://localhost:3300/product/insert', fd)
        .then((result) => {
          console.log(result)
        }).catch((err) => {
          console.log(err)
        })
    },
    addToCart (id) {
      alert(id)
    }
  },
  mounted () {
    this.getAll()
  }
}
</script>
