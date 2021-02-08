<template>
  <div>
    <b-table striped hover :items="items" :fields="fields">
      <template #cell(name)="data">
        {{ data.item.photographer.name }}
      </template>
      <template #cell(timeSlot)="data">
        {{ data.item.timeSlot.starts | formatTime }} -
        {{ data.item.timeSlot.ends | formatTime }}
      </template>
    </b-table>
  </div>
</template>


<script lang='ts'>
import Vue from "vue";
import axios from "axios";
import moment from "moment";

export default Vue.extend({
  name: "AvailableTable",
  data() {
    return {
      fields: [
        { key: "name", label: "Full name" },
        { key: "timeSlot", label: "Time slot" },
      ],
      items: null,
    };
  },
  filters: {
    formatTime(value: any) {
      return moment(value).format("HH.mm");
    },
  },
  mounted() {
    axios
      .get(
        "http://localhost:8090/api/photographers/available?date=2020-11-25&bookingId=5"
      )
      .then(
        (response) => (
          (this.items = response.data.availablePhotographers),
          console.log(response.data.availablePhotographers)
        )
      )
      .catch((error) => console.log(error));
  },
});
</script>