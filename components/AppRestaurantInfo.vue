<template>
  <section class="restaurantinfo">
    <div v-for="store in datasource" :key="store.id">
      <h2>{{ store.name }}</h2>
      <p>Delivey Time {{ store.deliveryTime }}</p>
      <p>Rating {{ store.rating }}</p>
      <p v-if="store.freeDelivery" class="label">
        <span>Free Delivery</span>
      </p>

      <div class="row">
        <div
          class="items"
          v-for="menuitem in store.menu"
          :key="menuitem.key"
          :style="`background: url(${menuitem.img}) no-repeat center center`"
        >
          <div class="iteminfo">
            <div>
              <h4>{{ menuitem.item }}</h4>
              <p>{{ priceFormatting(menuitem.price) }}</p>
              <nuxt-link :to="`items/${menuitem.id}`">
                <button class="ghost">View Item</button>
              </nuxt-link>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    datasource: {
      type: [Array, Object]
    }
  },
  methods: {
    priceFormatting(item) {
      return "$" + item.toFixed(2);
    }
  }
};
</script>

<style lang="scss" scoped></style>
