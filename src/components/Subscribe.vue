<template>
    <div class="Subscribe">
        <div class="letter_container">
            <div :style="{color : title_letter_color }" class="title_letter">{{ title_letter }}</div>
            <div :style="{color : desc_letter_color }" class="desc_letter">{{ desc_letter }}</div>
            <div class="subscribe_container">
                <i class="uil uil-message"></i>
                <input type="text" placeholder="Your email address.">
                <button class="subscribe_button">Subscribe</button>
            </div>
        </div>

        <img :src='image_background' class="img_background"/>
        <img :src='image_frontground' class="img_frontground"/>
    </div>
</template>

<script>

export default{
    props: ["image_background", "image_frontground", "title_letter", "title_letter_color",  "desc_letter", "desc_letter_color"],
};

</script>

<style scoped>

.Subscribe{
    width: 1384px;
    height: 538px;
    background-color: rgba(253, 192, 64, 0.2);
    position: relative;
    border-radius: 30px;
    overflow: hidden;
}

.letter_container{
    height: 538px;
    display: flex;
    flex-direction: column;
    gap: 30px;
    position: relative;
    z-index: 2;
    justify-content: center;
    left: 8vh;
}

.title_letter{
    width: 727px;
    font-family: quicksand;
    font-size: 72px;
    font-weight: 700;
}

.desc_letter{
    width: 727px;
    font-family: Lato;
    font-size: 30px;
    font-weight: 400;
}

.subscribe_container{
    width: 442px;
    display: flex;
    background-color: white;
    border-radius: 30px;
    justify-content: space-between;
    align-items: center;
}

i{
    color: rgba(126, 126, 126, 1);
    font-size: 24px;
    padding-left: 22px;
}

input{
    width: 125px;
    border: none;
    outline: none;
}

input::placeholder{
    color: rgba(182, 182, 182, 1);
    font-family: Lato;
    font-size: 12px;
    font-weight: 400;
}

.subscribe_button{
    width: 149px;
    height: 50px;
    background-color: rgba(59, 183, 126, 1);
    border: none;
    border-radius: 30px;
    color: white;
    font-family: quicksand;
    font-size: 16px;
    font-weight: 700;
}

.img_background{
    position: absolute;
    top: 0 ;
    z-index: 1;
}

.img_frontground{
    position: absolute;
    right: 0;
    bottom: 0;
}

</style>