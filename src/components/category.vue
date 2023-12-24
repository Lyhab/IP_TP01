<template>
    <router-link :to="`/categories/${id}`">
        <div :style="{ backgroundColor : bg_color }" class="Categories">
        <div class="img_container"><img :src='image'/></div>
        <div class="letter_container">
            <div class="title">{{ title }}</div>
            <div class="amount">{{ amount }} items</div>
        </div>
    </div>
    </router-link>
</template>

<script>

export default{
    props: ["image", "title", "bg_color", "amount", "id"]
};

</script>

<style scoped>

.Categories{
    width: 136px;
    height: 185px;
    border: none;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.img_container{
    width: 100%;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: start;
}

.letter_container{
    width: 100%;
    height: 85px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 5px;
}

.title{
    font-family: quicksand;
    font-size: 16px;
    font-weight: 700;
    color: #253D4E;
}

.amount{
    font-family: lato;
    font-size: 12px;
    font-weight: 400;
    color: #B6B6B6;
}

</style>