<template>
  <nav>
    <ul>
      <li>
        <nuxt-link exact to="/">
          <AppLogo />
        </nuxt-link>
      </li>
      <li>
        <nuxt-link to="/restaurantinfo">Restaurants</nuxt-link>
      </li>
    </ul>
    <div class="smallnum">
      {{ totalAmount }}
    </div>
    <nuxt-link to="/cart">Cart</nuxt-link>
  </nav>
</template>

<script>
import AppLogo from "@/components/AppLogo.vue";
import { mapGetters } from "vuex";

export default {
  components: {
    AppLogo
  },
  computed: {
    ...mapGetters(["totalAmount"])
  }
};
</script>

<style lang="scss" scoped></style>
