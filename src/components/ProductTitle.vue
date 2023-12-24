<template>
    <div class="title">{{ title }}</div>
</template>

<script>
export default {
    props: ["title"],
};
</script>

<style scoped>
.title {
    font-family: Quicksand;
    font-weight: 700;
    font-size: 40px;
    color: #253D4E;
}
</style>
