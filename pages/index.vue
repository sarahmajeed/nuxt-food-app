<template>
  <div class="container">
    <AppHeader />
    <AppRestaurantInfo :datasource="fooddata" />
  </div>
</template>

<script>
import AppHeader from "@/components/AppHeader.vue";
import AppRestaurantInfo from "@/components/AppRestaurantInfo.vue";
import { mapState } from "vuex";
export default {
  computed: {
    ...mapState(["fooddata"])
  },
  methods: {},
  components: {
    AppHeader,
    AppRestaurantInfo
  }
};
</script>

<style></style>
