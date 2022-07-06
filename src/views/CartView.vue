<template>
  <div class="cart">
    <h1 class="cart__title">Корзина</h1>
    <div>
      <TableCart :products_data="PRODUCTS" />
    </div>
  </div>
</template>

<script>
import TableCart from "@/components/TableCart.vue";
import { mapActions, mapGetters } from "vuex";

export default {
  name: "CartView",
  components: {
    TableCart,
  },
  computed: {
    ...mapGetters(["PRODUCTS"]),
  },
  methods: {
    ...mapActions(["GET_PRODUCTS_FROM_API"]),
  },
  mounted() {
    this.GET_PRODUCTS_FROM_API();
  },
};
</script>
