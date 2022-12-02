<template>
  <nav>
    <router-link
      to="/"
      class="nav-text"
      style="display: inline-block; text-decoration: none"
      >Mens Cloth</router-link
    >
    |
    <router-link
      to="/woman"
      class="nav-text"
      style="display: inline-block; text-decoration: none"
      >Womans Cloth</router-link
    >
    |
    <router-link
      to="/unavailable"
      class="nav-text"
      style="display: inline-block; text-decoration: none"
      >Unavailable</router-link
    >
  </nav>
</template>

<script>
export default {
  name: "NavbarView",
};
</script>

<style>
nav {
  text-align: center;
  margin: auto;
  background-color: transparent;
}
.nav-text {
  font-family: "inter", sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 22px;
  color: #1e1e1e;
}
</style>
