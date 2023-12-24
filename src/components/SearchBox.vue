<template>
    <div class="search_box_container">
        <div class="left_side">
            <div class="left_left_side">
                <div class="left_title" :style="{color : title_color, fontSize : title_size}">{{ title_text }}</div>
                <i :class="left_icon" :style="{color : left_icon_color, fontSize : left_icon_size}"></i>
            </div>

            <div class="left_right_side"> | </div>
        </div>

        <div class="middle_side">
            <input type="text" class="input" :placeholder="placeholder">
        </div>

        
        <div class="right_side">
            <i :class="right_icon" :style="{color : right_icon_color, fontSize : right_icon_size}"></i>
        </div>
    </div>
</template>


<script>

export default{
    props: ["title_color", "title_size", "title_text", "left_icon", "left_icon_color", "left_icon_size", "placeholder", "right_icon", "right_icon_color", "right_icon_size"]
};

</script>

<style scoped>

.search_box_container{
    width: 700px;
    height: 50px;
    display: flex;
    align-items: center;
    border: 2px solid #BCE3C9;
    border-radius: 5px;
}

.left_side{
    width: 190px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 14px;
}

.left_left_side{
    display: flex;
    align-items: center;
    gap: 14px;
}

.left_title{
    font-family: quicksand;
    font-size: 14px;
    font-weight: 700;
}

.left_right_side{
    color: #CACACA;
}

.middle_side{
    width: 470px;
}

.input{
    width: 450px;
    background-color: transparent;
    outline: none;
    border: none;
}

</style>