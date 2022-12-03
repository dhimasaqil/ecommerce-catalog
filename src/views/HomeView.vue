<template>
  <div>
    <div class="container-content-man">
      <div>
        <loaderVue v-if="isLoading" />
        <div v-else>
          <unavailableCard
            :product="products"
            v-if="category == 2"
            :increment="increment"
          />
          <CardView :product="products" :increment="increment" v-else />
        </div>
      </div>
      <!-- <unavailableCard /> -->
    </div>
    <div class="bg-man" v-if="category == 0"></div>
    <div class="bg-woman" v-else-if="category === 1"></div>
    <div class="bg-unavailable" v-else></div>
  </div>
</template>

<script>
// @ is an alias to /src
import CardView from "@/components/Card.vue";
import loaderVue from "@/components/loader.vue";
import unavailableCard from "@/components/UnavailableCard.vue";
import axios from "axios";
export default {
  name: "HomeView",
  components: {
    CardView,
    loaderVue,
    unavailableCard,
  },
  data() {
    return {
      products: [],
      number: 1,
      isLoading: true,
      category: 0,
    };
  },
  methods: {
    setProduct(data) {
      this.products = data;
    },
    increment() {
      if (this.number >= 20) {
        this.number = 1;
      } else {
        this.number = this.number + 1;
        console.log("data", this.number);
      }
    },
  },
  mounted() {
    console.log("data", this.number);
    this.isLoading = true;
    axios
      .get("https://fakestoreapi.com/products/" + this.number)
      .then((response) => {
        if (response.data.category == "men's clothing") {
          this.category = 0;
          console.log("cowo");
        } else if (response.data.category == "women's clothing") {
          this.category = 1;
          console.log("cewe");
        } else {
          this.category = 2;
          console.log("lain");
        }
        console.log(response);
        this.setProduct(response.data);
        this.isLoading = false;
      })
      .catch((error) => console.log("Gagal : ", error));
  },
  watch: {
    number() {
      if (this.isLoading == false) {
        this.isLoading = true;
        axios
          .get("https://fakestoreapi.com/products/" + this.number)
          .then((response) => {
            if (response.data.category == "men's clothing") {
              this.category = 0;
              console.log("cowo");
            } else if (response.data.category == "women's clothing") {
              this.category = 1;
              console.log("cewe");
            } else {
              this.category = 2;
              console.log("lain");
            }
            this.setProduct(response.data);
            this.isLoading = false;
          })
          .catch((error) => console.log("Gagal : ", error));
      }
    },
  },
  updated() {
    // this.isLoading = true;
  },
};
</script>

<style>
* {
  margin: 0;
}
.container-content-man {
  position: absolute;
  background-color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  min-height: 100vh;
}
.bg-man {
  background-color: #d6e6ff;
  /* bottom: 0; */
  background-image: url(../assets/bg-pattern.svg);
  width: 100%;
  height: 70%;
  margin: 0;
  /* padding-top: 30px; */
  position: absolute;
  z-index: 0;
}
.bg-woman {
  background-color: #fde2ff;
  background-image: url(../assets/bg-pattern.svg);
  width: 100%;
  height: 548px;
  margin: 0;
  /* padding-top: 30px; */
  position: absolute;
  z-index: 0;
}
.bg-unavailable {
  background-color: #d8d7d7;
  background-image: url(../assets/bg-pattern.svg);
  width: 100%;
  height: 548px;
  margin: 0;
  /* padding-top: 30px; */
  position: absolute;
  z-index: 0;
}
</style>
