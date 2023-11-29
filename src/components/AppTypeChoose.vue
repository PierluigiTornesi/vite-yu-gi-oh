<script>
import { store } from '../store';

    export default {
     data() {
        return {
            store,
    };
  },
};
</script>

<template>
    <div class="back">
        <div class="container pb-3">
            <div class="select-div">
                <select class="form-select" aria-label="Default select example" v-model="store.selectedArc" @change="$emit('performSearch')">
                    <option disabled>Seleziona un archetype</option>
                    <option value="">Tutti</option>
                    <option value="Alien">Alien</option>
                    <option value="Ally of Justice">Ally of Justice</option>
                    <option value="Ancient Gear">Ancient Gear</option>
                    <option value="Baby">Baby</option>
                    <option value="Blue-Eyes">Blue-Eyes</option>
                </select>
            </div>
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