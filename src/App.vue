<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import { store } from "./store.js";
import AppTypeChoose from "./components/AppTypeChoose.vue";

export default {
  data() {
    return {
      store
    };
  },
  created() {
    this.store.loading = true;
    axios.get(this.store.apiUrl).then((resp) => {
      console.log(resp);
      this.store.characters = resp.data.data;
      this.store.loading = false;
    });
  },
  components: { AppHeader,AppTypeChoose },
};
</script>

<template>
  <AppHeader />
  <AppTypeChoose />
</template>

<style lang="scss">
@use "./style/general.scss";
</style>