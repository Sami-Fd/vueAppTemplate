<template>
  <v-card width="268" v-for="(item, idx) in items" :key="idx">
    <v-card-item>
      <v-row align="center" no-gutters>
        <v-col cols="6">
          <p>{{ item.title }}</p>
        </v-col>
        <v-col cols="6" class="text-right">
          <v-icon color="error" :icon="item.cardIcon" size="32"></v-icon>
        </v-col>
      </v-row>
    </v-card-item>

    <v-card-text class="pb-2">
      <v-row align="center" no-gutters>
        <v-col cols="6">
          <p>{{ item.value }}</p>
        </v-col>
        <v-col cols="6" class="text-right">
          <v-list-item density="compact" :prepend-icon="item.subIcon">
            <v-list-item-subtitle>{{ item.value }}</v-list-item-subtitle>
          </v-list-item>
        </v-col>
      </v-row>
    </v-card-text>

    <!-- 
        options: if you want to use the same component for different data,
        <div class="d-flex py-3 justify-space-between">
        <v-list-item density="compact" prepend-icon="mdi-weather-windy">
          <v-list-item-subtitle>123 km/h</v-list-item-subtitle>
        </v-list-item>
  
        <v-list-item density="compact" prepend-icon="mdi-weather-pouring">
          <v-list-item-subtitle>48%</v-list-item-subtitle>
        </v-list-item>
      </div> -->
  </v-card>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { Item } from "./CardInterfaces";

export default defineComponent({
  name: "CardTemplate",

  components: {},

  props: {
    items: {
      type: Array as () => Item[],
      required: true,
    },
  },

  data() {
    return {};
  },
});
</script>
