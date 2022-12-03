<template>
  <div class="container-card">
    <div class="main-container-unavailable">
      <p class="text-unavailable">This product is unavailable to show</p>
      <button class="btn-unavailable" @click="increment">Next product</button>
      <div class="bg-img">
        <img class="img-sad" src="../assets/sad-face.svg" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "UnavailableCard",
  props: ["product", "increment"],
};
</script>

<style>
.text-unavailable {
  font-family: "Inter", sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 20px;
  line-height: 24px;
  margin-bottom: 20px;
  color: #000000;
}
.btn-unavailable {
  box-sizing: border-box;
  width: 480px;
  height: 32px;
  color: #000;
  background: transparent;
  font-family: "Inter", sans-serif;
  font-style: normal;
  font-weight: 600;
  font-size: 20px;
  line-height: 24px;
  border-radius: 4px;
  border: 1px solid #000;
}
.main-container-unavailable {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 30px;
  /* position: absolute; */
  width: 1034px;
  height: 500px;
  /* align-content: center; */
  background: #ffffff;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 10px;
  z-index: 10;
  align-items: center;
}
.bg-img {
  width: 1034px;
  height: 500px;
  z-index: -1;
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
}
.img-sad {
  max-width: 80%;
  height: auto;
  margin-left: 150px;
}
</style>
