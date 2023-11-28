<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import { store } from "./store.js";
import AppTypeChoose from "./components/AppTypeChoose.vue";
import CharactersList from "./components/CharactersList.vue";

export default {
  data() {
    return {
      store
    };
  },
  created() {
    this.store.loading = true;
    axios.get(this.store.apiUrl).then((resp) => {
      this.store.characters = resp.data.data;
      this.store.loading = false;
    });
  },
  components: { AppHeader, AppTypeChoose, CharactersList },
  methods: {
    handleSearch() {
      console.log("Cerca");
      axios.get(this.store.apiUrl, {
          params: {
            archetype: this.store.searchText,
          },
        })
        .then((resp) => {
          this.store.characters = resp.data.data;
        });
    },
  },
};
</script>

<template>
  <AppHeader />
  <AppTypeChoose @performSearch="handleSearch"/>
  <CharactersList />
</template>

<style lang="scss">
@use "./style/general.scss";
</style>