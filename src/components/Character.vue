<template>
<div class="character text-center pb-4 mt-5">
    <img :src="item.image" :alt="item.name">
    <h3>{{ item.name }}</h3>
    <div class="fst-italic">{{ item.origin.name }}</div>
    <div class="fw-bold">{{ item.species }}</div>
</div>
</template>

<script>
export default {
    name: "Character",
    props: ["item"]
}
</script>

<style lang="scss" scoped>

    .character {

        img {
            height: 200px;
            border-radius: 50%;
        }
    }

</style>