<script>
import { store } from "../store";
import AppCard from "./AppCard.vue";
import AppLoader from "./AppLoader.vue";
import CharactersStats from "./CharactersStats.vue";

export default {
  data() {
    return {
      store,
    };
  },
  components: {
    AppCard,
    AppLoader,
    CharactersStats
},
};
</script>

<template>
  <section>
    <div class="container bg-white">
    <CharactersStats />
    <AppLoader v-if="store.loading" />
    <div class="row " v-else>
      <div class="col-2 m-3 " v-for="character in store.characters" :key="character.name">
        <AppCard :character="character" />
      </div>
    </div>
  </div>
  </section>
</template>

<style lang="scss" scoped>
section{
  background-color: #d48f38;
}
</style>