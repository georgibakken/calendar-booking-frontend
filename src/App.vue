<template>
  <div id="app">
    <AvailablePhotographers date="25th of November 2020 - 90 minutes" />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import AvailablePhotographers from "./components/AvailablePhotographers.vue";

export default Vue.extend({
  name: "App",
  components: {
    AvailablePhotographers,
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
