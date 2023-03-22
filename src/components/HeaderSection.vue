<template>
  <v-app-bar app :elevation="0">
    <v-btn variant="text" icon="mdi-menu" @click="rail = !rail"></v-btn>
    <v-toolbar-title>Admin Dashboard</v-toolbar-title>
    <v-spacer></v-spacer>
    <!-- <v-switch
      v-model="themeColor"
      :label="themeColor === 'light' ? 'Light' : 'Dark'"
      :color="themeColor === 'light' ? 'black' : 'white'"
      @change="themeColor === 'light' ? 'light' : 'dark'"
      hide-details
    ></v-switch> -->
    <v-menu>
      <template v-slot:activator="{ props }">
        <v-btn icon v-bind="props">
          <v-badge color="error" content="3">
            <v-icon>mdi-bell</v-icon>
          </v-badge>
        </v-btn>
      </template>
      <v-list>
        <v-list-item
          v-for="(item, index) in notifications"
          :key="index"
          :value="index"
          :prepend-icon="item.icon"
          :subtitle="item.subtitle"
        >
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
    <v-menu location="bottom">
      <template v-slot:activator="{ props }">
        <v-btn icon v-bind="props">
          <v-avatar size="32px">
            <img
              src="https://cdn.vuetifyjs.com/images/lists/1.jpg"
              alt="Avatar"
            />
          </v-avatar>
        </v-btn>
      </template>
      <v-list>
        <v-list-item
          v-for="(item, index) in items"
          :key="index"
          :value="index"
          :prepend-icon="item.icon"
        >
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
  </v-app-bar>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "HeaderSection",
  provide() {
    return {
      showSidebar: this.rail,
    };
  },
  data() {
    return {
      rail: true,
      themeColor: "light",
      items: [
        {
          title: "Profile",
          icon: "mdi-account",
        },
        {
          title: "Logout",
          icon: "mdi-logout",
        },
      ],
      notifications: [
        {
          title: "You have 5 new messages",
          icon: "mdi-email",
          subtitle: "2 min ago",
        },
        {
          title: "You have 3 new notifications",
          icon: "mdi-bell",
          subtitle: "5 min ago",
        },
      ],
    };
  },
  methods: {
    showSidebar() {
      this.rail = !this.rail;
      this.$emit("showSidebar", this.rail);
    },
  },
});
</script>
