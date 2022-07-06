<template>
  <nav>
    <router-link to="/">Главная</router-link> |
    <router-link to="/cart">Корзина</router-link>
  </nav>
  <router-view />
</template>

<script>
export default {
  name: "app",
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
