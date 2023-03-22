<template>
  <Doughnut :data="data" :options="options" v-if="chartType === 'doughnut'" />
  <Bar :data="dataBar" :options="options" v-if="chartType === 'bar'" />
</template>

<script lang="ts">
import {
  Chart as ChartJS,
  ArcElement,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale,
} from "chart.js";
import { Doughnut, Bar } from "vue-chartjs";
import { data, options } from "./chartConfigDoughnut";
import { dataBar } from "./chartConfigBar";

ChartJS.register(
  ArcElement,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale
);

export default {
  name: "App",
  components: {
    Doughnut,
    Bar,
  },
  props: {
    /*data: Object,
    options: Object,
    */
    chartType: String,
  },
  data() {
    return {
      data,
      options,
      dataBar,
    };
  },
};
</script>
