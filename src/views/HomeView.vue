<template>
  <div>
    <div class="container-content-man">
      <NavbarView />
      <div>
        <CardView :product="products" :increment="increment" />
      </div>
    </div>
    <div class="bg"></div>
  </div>
</template>

<script>
// @ is an alias to /src
import NavbarView from "@/components/navbar.vue";
import CardView from "@/components/Card.vue";
import axios from "axios";
export default {
  name: "HomeView",
  components: {
    CardView,
    NavbarView,
  },
  data() {
    return {
      products: [],
      number: 1,
    };
  },
  methods: {
    setProduct(data) {
      this.products = data;
    },
    increment() {
      this.number = this.number + 1;
      console.log("data", this.number);
    },
  },
  mounted() {
    console.log("data", this.number);
    axios
      .get("https://fakestoreapi.com/products/" + this.number)
      .then((response) => this.setProduct(response.data))
      .catch((error) => console.log("Gagal : ", error));
  },
  updated() {
    axios
      .get("https://fakestoreapi.com/products/" + this.number)
      .then((response) => this.setProduct(response.data))
      .catch((error) => console.log("Gagal : ", error));
  },
};
</script>

<style>
* {
  margin: 0;
}
.container-content-man {
  background-color: #d6e6ff;
  background-image: url(../assets/bg-pattern.svg);
  width: 100%;
  height: 600px;
  margin: 0;
  padding-top: 30px;
  position: absolute;
}
.bg {
  position: absolute;
  bottom: 0;
  background-color: #fff;
  width: 100%;
  height: 300px;
  z-index: 0;
}
</style>
