<template>
    <button :style="{ backgroundColor : button_bg_color , color : button_color}" class="Button">{{ text }} <i class="uil uil-arrow-right"></i></button>
</template>

<script>

    export default {
        name: "Buttons",
        props: ["text", "button_color", "button_bg_color"],
    };

</script>

<style>

.Button{
    font-family: quicksand;
    font-size: 12px;
    font-weight: bold;
    border: none;
    border-radius: 2px;
    height: 31px;
    width: 110px;
    display: flex;
    gap: 1vh;
    align-items: center;
    justify-content: center;
}

i{
    font-size: 18px;
}
</style>