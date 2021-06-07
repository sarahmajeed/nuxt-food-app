<template>
  <div>
    <div class="content">
      <AppMenu />
      <Nuxt />
    </div>
    <footer class="footer">
      <p>Copyright &copy;</p>
    </footer>
  </div>
</template>

<script>
import AppMenu from "@/components/AppMenu.vue";
export default {
  AppMenu
};
</script>

<style>
html {
  font-family: "Poppins", sans-serif;
  font-weight: 300;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
</style>
