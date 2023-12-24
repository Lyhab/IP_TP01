<template>
    <div class="bot_desc">
        <div v-html="description"></div>
    </div>
</template>

<script>
export default {
    props: ["description"],
};
</script>

<style scoped>
.bot_desc {
    width: 90%;
    font-family: Lato;
    font-size: 16px;
    font-weight: 400;
    color: rgba(126, 126, 126, 1);
}
</style>
