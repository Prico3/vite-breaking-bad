<script>
export default {
    props: {
        character: Object
    }
}
</script>

<template>
    <div class="card p-3 text-center mt-3">
        <img :src="character.img" alt="">
        <h3>{{ character.name }}</h3>
        <h4>{{ character.category }}</h4>
        <h4>{{ character.status }}</h4>
    </div>
</template>

<style lang="scss" scoped>
.card {
    background-color: #2e3a46;

    h3 {
        color: white;
        font-size: medium;
        margin: 0.5rem 0;
    }

    h4 {
        color: lightgrey;
        font-size: small;
        font-weight: 300;
    }
}
</style>
