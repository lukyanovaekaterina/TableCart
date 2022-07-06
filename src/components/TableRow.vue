<template>
  <tr class="table__row">
    <td class="row__id"><input type="checkbox" />{{ row_data.id }}</td>
    <td class="row__img">{{ row_data.img }}</td>
    <td class="row__name">{{ row_data.name }}</td>
    <td class="row__price">{{ row_data.price }} p</td>
    <td class="row__quantity">
      {{ row_data.quantity }}
    </td>
    <td class="row__sum">{{ PositionSumCart }} p.</td>
  </tr>
</template>

<script>
export default {
  name: "TableRow",
  props: {
    row_data: {
      type: Object,
      default: () => {
        return {};
      },
    },
  },
  computed: {
    PositionSumCart() {
      let result = [];
      result.push(this.row_data.price * this.row_data.quantity);
      return result;
    },
  },
};
</script>

<style>
td {
  flex-basis: calc(100% / 6);
  text-align: left;
}

.table__row {
  display: flex;
  justify-content: space-around;
  height: 40px;
}
</style>
