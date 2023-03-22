<template>
  <v-card elevation="0">
    <v-card-title>
      <p>{{ pageTitle }}</p>
    </v-card-title>
    <v-card-text>
      <router-view></router-view>
    </v-card-text>
  </v-card>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "ContentSection",
  data(): any {
    return {
      pageTitle: "",
    };
  },
  watch: {
    $route(to, from: any) {
      console.log("to.meta.title", to);
      this.pageTitle = to.name || "";
    },
  },
});
</script>
