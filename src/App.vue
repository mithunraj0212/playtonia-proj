<template>
  <v-app>
    <v-container>
      <v-row>
        <v-col sm="4" md="3" v-for="data in $store.state.response.data" :key="data.id">
          <Card :msg="data" />
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
import Card from "./components/Card.vue";
import axios from "axios";
export default Vue.extend({
  name: "App",

  components: {
    Card,
  },
  mounted() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos/")
      .then((response) => {
        this.$store.state.response = response;
      });
  },
  data: () => ({
    //
  }),
});
</script>
