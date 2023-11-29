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
      this.store.loading = true;
      console.log("Cerca");
      
      if(this.store.selectedArc !== ""){
        axios.get(this.store.apiUrl, {
          params: {
            archetype: this.store.selectedArc,
          },
        })
        .then((resp) => {
          this.store.characters = resp.data.data;
        })
        .catch((err) => {
          alert("valore non valido");
        })
        .finally(() =>{
          this.store.loading = false;
        });
      }else{
        axios.get(this.store.apiUrl).then((resp) => {
        this.store.characters = resp.data.data;
        this.store.loading = false;
    });
      }
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