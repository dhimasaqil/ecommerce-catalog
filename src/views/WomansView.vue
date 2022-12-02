<template>
  <div class="woman">
    <div class="container-content-woman">
      <NavbarView />
      <CardView />
    </div>
    <div class="bg"></div>
  </div>
</template>
<script>
import NavbarView from "@/components/navbar.vue";
import CardView from "@/components/Card.vue";
export default {
  name: "HomeView",
  components: {
    NavbarView,
    CardView,
  },
};
</script>
<style>
.container-content-woman {
  background-color: #fde2ff;
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
