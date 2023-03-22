<template>
  <v-table>
    <thead>
      <tr>
        <th class="text-left" v-for="(item, idx) in tableColumns" :key="idx">
          {{ item }}
        </th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in tableItems" :key="item.name">
        <td>{{ item.name }}</td>
        <td>{{ item.calories }}</td>
        <td>{{ item.fat }}</td>
        <td>{{ item.carbs }}</td>
        <td>{{ item.protein }}</td>
        <td>{{ item.iron }}</td>
      </tr>
    </tbody>
  </v-table>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { Dessert } from "./TableInterfaces";

export default defineComponent({
  name: "TableTemplate",

  props: {
    tableItems: {
      type: Array as () => Dessert[],
      required: true,
    },
    tableColumns: {
      type: Array as () => string[],
      required: true,
    },
  },

  data() {
    return {};
  },
});
</script>
