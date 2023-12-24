<template>
    <router-link :to="`/products/${id}`">
        <div :style="{ backgroundColor : bg_color }" class="Promotions">
            <div class="letter_container">
                <div :style="{color : letter_color }" class="letter">{{ letter }}</div>
                <Buttons :text="text" :button_color="button_color" :button_bg_color="button_bg_color" class="button"/>
            </div>
            <img :src='image' class="img"/>
        </div>
    </router-link>
    
</template>

<script>
import Buttons from './button.vue'

export default{
    props: ["image", "letter", "letter_color", "bg_color", "button_color", "button_bg_color", "text", "id"],
    components: {
        Buttons,
    }
};

</script>

<style scoped>

.Promotions{
    width: 490px;
    height: 300px;
    border: none;
    border-radius: 10px;
    position: relative;
    overflow: hidden;
}

.img{
    position: absolute;
    z-index: 0;
    bottom: 0;
    right: 0;
    border-radius: 10px;
}

.letter_container{
    width: 512px;
    height: 300px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 4vh;
    margin-left: 48px;
}

.letter{
    width: 271px;
    z-index: 1;
    font-size: 24px;
    font-weight: 700;
    font-family: quicksand;
    color: #253D4E;
    display: flex;
    justify-content: center;
    align-items: center;
}

.button{
    z-index: 1;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>