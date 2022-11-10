<script>
import { store } from '../store';
import cardApp from './cardApp.vue';
export default {
    name: "MainApp",
    data() {
        return {
            store
        };
    },
    components: { cardApp }
}
</script>

<template>

    <div class="ms_container mt-5 flex">
        <div class="col " v-for="item in store.characters" :key="item.id">
            <cardApp :character="item" />
        </div>
    </div>

</template>

<style lang="scss" scoped>
.ms_container {
    width: 60%;
    margin: 0 auto;
    background-color: white;
}
</style>