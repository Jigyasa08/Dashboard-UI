<template>
  <DashboardView />
</template>

<script>
import DashboardView from "./components/DashboardView.vue";

export default {
  name: "App",
  components: {
    DashboardView,
  },
};
</script>

<style>
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 0;
}
</style>
