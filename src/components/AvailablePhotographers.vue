<template>
  <div>
    <h1>Available photographers</h1>
    <h2>{{ date }}</h2>
    <AvailableTable />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import AvailableTable from "./AvailableTable.vue";

export default Vue.extend({
  name: "AvailablePhotographers",
  props: {
    date: String,
  },
  components: {
    AvailableTable,
  },
});
</script>