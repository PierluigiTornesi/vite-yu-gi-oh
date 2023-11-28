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
    <div class="container text-white number">
        <h6>Found  {{ store.characters.length }} cards</h6>
    </div>
</template>


<style lang="scss" scoped>
.number{
  background-color: #212529;
  padding: 1rem;
}
</style>