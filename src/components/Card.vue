<template>
  <div class="container-card">
    <div class="main-container">
      <div class="card-image">
        <img :src="product.image" alt="" />
      </div>
      <div class="desc-product">
        <h4>{{ product.title }}</h4>
        <div class="rat-product">
          <p class="cat-product">{{ product.category }}</p>
          <p class="rating"></p>
        </div>

        <hr />
        <p class="deskripsi">{{ product.description }}</p>
        <hr />
        <h4>{{ product.price }}</h4>
        <div class="button-wrap">
          <button class="btn-buy">Buy now</button>
          <button class="btn-next" @click="increment">Next product</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardView",
  props: ["product", "increment"],
};
</script>

<style>
hr {
  margin-bottom: 10px;
}
.button-wrap {
  display: flex;
  justify-content: space-between;
}
.btn-buy {
  box-sizing: border-box;
  width: 239px;
  height: 32px;
  color: white;
  font-family: "Inter", sans-serif;
  font-style: normal;
  font-weight: 600;
  font-size: 20px;
  line-height: 24px;
  background: #002772;
  border-radius: 4px;
  border: none;
}
.btn-next {
  box-sizing: border-box;
  width: 239px;
  height: 32px;
  color: #002772;
  background: transparent;
  font-family: "Inter", sans-serif;
  font-style: normal;
  font-weight: 600;
  font-size: 20px;
  line-height: 24px;
  border-radius: 4px;
  border: 1px solid #002772;
}
img {
  /* border: 1px solid black; */
  max-height: 500px;
  max-width: 480px;
  margin-left: 30px;
}
h4 {
  font-family: "Inter", sans-serif;
  font-style: normal;
  margin-bottom: 20px;
  font-weight: 600;
  font-size: 28px;
  line-height: 34px;
  color: #002772;
}
.deskripsi {
  font-family: "Inter", sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 24px;
  height: 300px;
  color: #1e1e1e;
}
.desc-product {
  /* border: 1px solid black; */
  height: 100%;
  width: 50%;
  padding: 10px;
  display: flex;
  /* justify-content: space-between; */
  flex-direction: column;
  color: #3f3f3f;
}
.rat-product {
  display: flex;
  justify-content: space-between;
  font-family: "Inter", sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 22px;
  margin-bottom: 10px;
}
.container-card {
  display: flex;
  justify-content: center;
  width: 100%;
  height: 300px;
  margin-top: 20px;
}
.main-container {
  display: flex;
  justify-content: space-between;
  padding: 30px;
  /* position: absolute; */
  width: 1034px;
  height: 500px;
  /* align-content: center; */
  background: #ffffff;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 10px;
  z-index: 10;
}
</style>
