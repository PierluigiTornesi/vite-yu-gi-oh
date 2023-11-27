<script>
export default {
  props: {
    character: Object,
  },
};
</script>

<template>
  <div class="text-center">
      <img :src="character.card_images[0].image_url" alt="immagine carta"/>
      <div class="back d-flex flex-column justify-content-around ">
      <h5 class="text-white">{{ character.name }}</h5>
      <span>{{ character.archetype }}</span>
      <span>{{  character.type }}</span>
    </div>
  </div>
</template>

<style lang="scss" scoped>

.back{
  background-color: #d48f38;
  min-height: 150px;
}

img{
  max-width: 100%;
}
</style>