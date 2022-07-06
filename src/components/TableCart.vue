<template>
  <div class="table">
    <table>
      <tbody>
        <TableRow v-for="row in products_data" :key="row.id" :row_data="row" />
        <tr class="cart__total">
          ИТОГО:
          {{
            TableTotalCart
          }}
          р
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import TableRow from "./TableRow.vue";

export default {
  name: "TableCart",
  components: {
    TableRow,
  },
  props: {
    products_data: {
      type: Array,
      default: () => {
        return [];
      },
    },
  },
  computed: {
    TableTotalCart() {
      let result = [];

      for (let item of this.products_data) {
        result.push(item.price * item.quantity);
      }

      result = result.reduce(function (sum, el) {
        return sum + el;
      });

      return result;
    },
  },
};
</script>

<style>
.table {
  max-width: 900px;
  margin: 0 auto;
}

table {
  width: 100%;
}
</style>
