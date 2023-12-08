<template>
    <div class="container">
        <div class="left_side">
            <i :class="browse_left_icon" :style="{color : browse_left_icon_color, fontSize : browse_left_icon_size}"></i>
            <div class="middle_text" :style="{color : browse_text_color}">{{ browse_text }}</div>
            <i :class="browse_right_icon" :style="{color : browse_right_icon_color, fontSize : browse_right_icon_size}"></i>
        </div>

        <div class="middle_side">
            <menuitem v-for="menuitem in store.menuitems.slice(4, 12)" :key="menuitem.id" :id="menuitem.id" :first_icon="menuitem.first_icon" :text="menuitem.text" :second_icon="menuitem.second_icon" :first_icon_color="menuitem.first_icon_color" :text_color="menuitem.text_color" :second_icon_color="menuitem.second_icon_color" :first_icon_size="menuitem.first_icon_size" :text_size="menuitem.text_size" :second_icon_size="menuitem.second_icon_size"></menuitem>
        </div>

        <div class="right_side">
            <i :class="right_icon" :style="{color : right_icon_color, fontSize : right_icon_size}"></i>
            <div class="right_container">
                <div class="right_tel" :style="{color : tel_color, fontSize : tel_size}">{{ tel }}</div>
                <div class="right_desc">24/7 Support Center</div>
            </div>
        </div>
    </div>
</template>

<script>
import { useStore } from '../stores/store'
import menuitem from '../components/menuitem.vue'

export default {
  props: ["browse_left_icon", "browse_left_icon_color", "browse_left_icon_size", "browse_text_color", "browse_text", "browse_right_icon", "browse_right_icon_color", "browse_right_icon_size", "right_icon", "right_icon_color", "right_icon_size", "tel", "tel_color", "tel_size"],
  components: {
    menuitem,
  },
  setup() {
    const store = useStore();
    return { store };
  },
};
</script>

<style scoped>
@import "https://unicons.iconscout.com/release/v4.0.8/css/line.css";
@import url('https://fonts.googleapis.com/css2?family=Knewave&family=Montserrat:wght@400;700&family=Quicksand:wght@600&family=Silkscreen:wght@400;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Knewave&family=Lato&family=Montserrat:wght@400;700&family=Quicksand:wght@600&family=Silkscreen:wght@400;700&display=swap');


.container{
  width: 100%;
  height: 70px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-top: 1px solid lightgray;
  border-bottom: 1px solid lightgray;
}

.left_side{
    width: 250px;
    height: 44px;
    background-color: #3BB77E;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 9px;
    border-radius: 5px;
}

.middle_text{
    font-family: quicksand;
    font-size: 16px;
    font-weight: 700;
}

.middle_side{
    width: 900px;
    padding-left: 54px;
    display: flex;
    align-items: center;
    gap: 40px;
}

.right_side{
    width: 200px;
    display: flex;
    align-items: center;
    justify-content: end;
    gap: 13px;
}

.right_container{
    width: 150px;
    display: flex;
    flex-direction: column;
}

.right_tel{
    font-size: 40px;
    font-family: quicksand;
    font-weight: 700;
    color: #3BB77E;
}

.right_desc{
    font-size: 15px;
    font-family: Lato;
    font-weight: 400;
    color: #7E7E7E;
}


</style>