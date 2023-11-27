<script>
import CharactersList from "./CharactersList.vue";
import CharactersStats from "./CharactersStats.vue";

    export default {
     data() {
        return {
    
    };
  },
  components: { CharactersList, CharactersStats},
};
</script>

<template>
    <div class="back">
        <div class="container pb-3">
            <div class="select-div">
                <select class="form-select" aria-label="Default select example">
                    <option selected>Alien</option>
                    <option value="1">Mage</option>
                    <option value="2">Dragon</option>
                    <option value="3">Demon</option>
                </select>
            </div>
        </div>
        <div class="container bg-light">
            <br>
            <CharactersStats />
            <CharactersList />
        </div>
    </div>
</template>

<style lang="scss" scoped>

.back{
    background-color: #d48f38;
    padding: 1rem;

    .select-div{
        width: 20%;
    }
}
</style>