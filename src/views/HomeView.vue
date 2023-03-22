<template>
  <div class="d-flex justify-space-between my-2">
    <card-template :items="items" />
  </div>
  <div class="my-4">
    <v-row>
      <v-col cols="12" md="6" lg="6" class="py-0">
        <chart-template chart-type="bar" />
      </v-col>
      <v-col cols="12" md="6" lg="6" class="py-0">
        <chart-template chartType="doughnut" />
      </v-col>
    </v-row>
  </div>
  <div>
    <table-template :table-items="desserts" :table-columns="columns" />
  </div>
  <!-- <v-card elevation="0">
    <v-card-title>
      <p>Data Table</p>
    </v-card-title>
    <v-card-text>
      <table-template :table-items="desserts" :table-columns="columns" />
    </v-card-text>
  </v-card> -->
</template>

<script lang="ts">
import CardTemplate from "@/components/card/CardTemplate.vue";
import TableTemplate from "@/components/table/TableTemplate.vue";
import ChartTemplate from "@/components/charts/ChartTemplate.vue";
import { defineComponent } from "vue";

export default defineComponent({
  name: "HomeView",

  components: {
    CardTemplate,
    TableTemplate,
    ChartTemplate,
  },

  data() {
    return {
      columns: ["Dessert", "Calories", "Fat", "Carbs", "Protein", "Iron"],
      desserts: [
        {
          name: "Frozen Yogurt",
          calories: 159,
          fat: 6.0,
          carbs: 24,
          protein: 4.0,
          iron: "1%",
        },
        {
          name: "Ice cream sandwich",
          calories: 237,
          fat: 9.0,
          carbs: 37,
          protein: 4.3,
          iron: "1%",
        },
        {
          name: "Eclair",
          calories: 262,
          fat: 16.0,
          carbs: 23,
          protein: 6.0,
          iron: "7%",
        },
      ],
      items: [
        {
          title: "Total Users",
          value: "100",
          cardIcon: "mdi-account",
          subIcon: "mdi-weather-windy",
        },
        {
          title: "Total Orders",
          value: "100",
          cardIcon: "mdi-cart",
          subIcon: "mdi-weather-pouring",
        },
        {
          title: "Total Revenue",
          value: "100",
          cardIcon: "mdi-currency-usd",
          subIcon: "mdi-weather-sunny",
        },
        {
          title: "Total Expenses",
          value: "100",
          cardIcon: "mdi-currency-usd",
          subIcon: "mdi-weather-sunny",
        },
      ],
    };
  },
});
</script>

CardTemplate
