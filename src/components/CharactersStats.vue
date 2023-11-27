<script>
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="container">
    <div class=" text-white number">
      <h6>Totale {{ store.characters.length }} personaggi</h6>
    </div>
  </div>
</template>


<style lang="scss" scoped>
.number{
  background-color: #212529;
  padding: 1rem;
}
</style>