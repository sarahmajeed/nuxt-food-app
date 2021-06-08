<template>
  <main class="container restaurant">
    <div class="restauantheading">
      <h1>Restauants</h1>
      <AppSelect @change="selectedRestaurant = $event" />
      <pre>{{ $data }}</pre>
    </div>
    <AppRestaurantInfo :datasource="filteredRestaurants" />
  </main>
</template>

<script>
import AppRestaurantInfo from "@/components/AppRestaurantInfo.vue";
import AppSelect from "@/components/AppSelect.vue";
import { mapState } from "vuex";

export default {
  data() {
    return {
      selectedRestaurant: ""
    };
  },
  components: {
    AppRestaurantInfo,
    AppSelect
  },
  computed: {
    ...mapState(["fooddata"]),
    filteredRestaurants() {
      if (this.selectedRestaurant) {
        return this.fooddata.filter(el => {
          let name = el.name.toLowerCase();
          return name.includes(this.selectedRestaurant);
        });
      }
      return this.fooddata;
    }
  }
};
</script>

<style lang="scss" scoped></style>
