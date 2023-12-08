<template>
    <router-link :to="`/categories/${id}`">
        <div class="menu_item_container">
            <div class="menu_part">
                <i :class="first_icon" :style="{color : first_icon_color, fontSize : first_icon_size}"></i>
                <div :style="{color : text_color, fontSize : text_size}">{{ text }}</div>
                <i :class="second_icon" :style="{color : second_icon_color, fontSize : second_icon_size}"></i>
            </div>
            
        </div>
    </router-link>
</template>


<script>

export default{
    props: ["first_icon", "text", "second_icon", "first_icon_color", "text_color", "second_icon_color", "first_icon_size", "text_size", "second_icon_size", "id"]
};

</script>

<style scoped>
@import "https://unicons.iconscout.com/release/v4.0.8/css/line.css";
@import url('https://fonts.googleapis.com/css2?family=Knewave&family=Montserrat:wght@400;700&family=Quicksand:wght@600&family=Silkscreen:wght@400;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Knewave&family=Lato&family=Montserrat:wght@400;700&family=Quicksand:wght@600&family=Silkscreen:wght@400;700&display=swap');

.menu_item_container{
    display: flex;
    gap: 2px;
    font-size: 16px;
    font-family: Lato;
    font-weight: 400;
}

.menu_part{
    display: flex;
    align-items: center;
}
</style>