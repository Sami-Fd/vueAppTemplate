<template>
  <v-theme-provider :theme="themeColor" with-background>
    <v-app>
      <Header></Header>
      <v-content>
        <v-container fluid class="px-0">
          <v-row>
            <v-col cols="12" md="4" lg="2" class="py-0">
              <SideBar class="mt-15" fluid />
            </v-col>
            <v-col cols="12" md="8" lg="10" class="py-0">
              <Content class="mt-15" />
            </v-col>
          </v-row>
        </v-container>
      </v-content>
    </v-app>
  </v-theme-provider>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Header from "./components/HeaderSection.vue";
import SideBar from "./components/SideBar.vue";
import Content from "./components/ContentSection.vue";

export default defineComponent({
  name: "App",
  components: {
    Header,
    SideBar,
    Content,
  },
  data() {
    return {
      pageTitle: "",
      themeColor: "light",
    };
  },

  watch: {
    $route(to, from: any) {
      this.pageTitle = to.meta.title || "Dashboard";
    },
  },
});
</script>

<style scoped></style>
