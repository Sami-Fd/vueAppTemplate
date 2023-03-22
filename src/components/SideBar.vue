<template>
  <v-layout>
    <v-navigation-drawer floating class="overflow-y-auto">
      <v-list density="compact" nav v-for="(item, idx) in items" :key="idx">
        <v-list-item
          :prepend-icon="item.icon"
          :title="item.title"
          link
          :to="item.to"
          :rail="rail"
          exact
        ></v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main class="h-screen"></v-main>
  </v-layout>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "SideBar",
  inject: ["showSidebar"],
  data() {
    return {
      rail: this.showSidebar,
      items: [
        { title: "Home", icon: "mdi-home", to: "/" },
        { title: "About", icon: "mdi-information", to: "/about" },
        { title: "Contact", icon: "mdi-email", to: "/contact" },
      ],
    };
  },
  methods: {
    getValue(value: any) {
      console.log("value", value);
    },
  },
});
</script>
