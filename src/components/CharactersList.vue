<script>
import { store } from "../store";
import AppCard from "./AppCard.vue";
import AppLoader from "./AppLoader.vue";

export default {
  data() {
    return {
      store,
    };
  },
  components: { 
    AppCard,
    AppLoader 
  },
};
</script>

<template>
    <div class="container">
    <AppLoader v-if="store.loading" />
    <div class="row " v-else>
      <div class="col-2 m-3 " v-for="character in store.characters" :key="character.name">
        <AppCard :character="character" />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
</style>