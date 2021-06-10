<template>
  <main class="container cart">
    <div v-if="cart.length">
      <h1>Cart</h1>

      <table>
        <thead>
          <tr>
            <th>Item</th>
            <th>Add Ons</th>
            <th>Amount</th>
            <th>Total Price</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in cart" :key="item.id">
            <td>
              {{ item.item }}
              <span v-if="item.otpions">- {{ item.options }}</span>
            </td>
            <td>
              <span v-for="addon in item.addOns" class="comma" :key="addon">
                {{ addon }}
              </span>
            </td>
            <td>{{ item.count }}</td>
            <td>{{ item.combinedPrice }}</td>
          </tr>
          <tr>
            <td colspan="3"></td>
            <td class="total">Total: ${{ totalPrice.toFixed(2) }}</td>
          </tr>
        </tbody>
      </table>
    </div>

    <div v-else>
      <AppEmptyCart />
    </div>
  </main>
</template>

<script>
import { mapState } from "vuex";
import { mapGetters } from "vuex";
import AppEmptyCart from "@/components/AppEmptyCart.vue";

export default {
  components: {
    AppEmptyCart
  },
  computed: {
    ...mapState(["cart"]),
    ...mapGetters(["totalPrice"])
  }
};
</script>

<style lang="scss" scoped></style>
