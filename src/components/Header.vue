<template>
    <div class="container">
        <router-link :to="`/`" class="top_left_side">
          <div class="icon_img_container">
            <img src="../assets/images/icon.svg" alt="" class="icon_img">
          </div>
          <div class="title_container">
            <div class="top_title">Melon</div>
            <div class="top_desc">MART & GROCERY</div>
          </div>
        </router-link>

        <div class="middle_search_box">
          <searchbox v-for="searchbox in store.searchboxes" :title_color="searchbox.title_color" :title_size="searchbox.title_size" :title_text="searchbox.title_text" :left_icon="searchbox.left_icon" :left_icon_color="searchbox.left_icon_color" :left_icon_size="searchbox.left_icon_size"  :placeholder="searchbox.placeholder" :placeholder_color="searchbox.placeholder_color" :right_icon="searchbox.right_icon" :right_icon_color="searchbox.right_icon_color" :right_icon_size="searchbox.right_icon_size"></searchbox>
        </div>

        <div class="right_menuitems_container">
          <menuitem v-for="menuitem in store.menuitems.slice(0, 4)" :key="menuitem.id" :id="menuitem.id" :first_icon="menuitem.first_icon" :text="menuitem.text" :second_icon="menuitem.second_icon" :first_icon_color="menuitem.first_icon_color" :text_color="menuitem.text_color" :second_icon_color="menuitem.second_icon_color" :first_icon_size="menuitem.first_icon_size" :text_size="menuitem.first_text_size" :second_icon_size="menuitem.second_icon_size"></menuitem>
        </div>
    </div>
</template>

<script>
import { useStore } from '../stores/store'
import menuitem from '../components/menuitem.vue'
import searchbox from '../components/SearchBox.vue'

export default {
  components: {
    menuitem,
    searchbox,
  },
  setup() {
    const store = useStore();
    return { store };
  },
};
</script>

<style scoped>

.container{
  width: 100%;
  height: 90px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: white;
}

.top_left_side{
  width: 300px;
  display: flex;
  gap: 9px;
}

.icon_img_container{
  display: flex;
  align-items: center;
}

.icon_img{
  width: 78px;
  height: 60px;
}

.title_container{
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.top_title{
  font-size: 40px;
  font-family: quicksand;
  font-weight: 700;
  color: #3BB77E;
  line-height: 1;
}

.top_desc{
  font-size: 13px;
  font-family: Montserrat;
  font-weight: 600;
  color: #253D4E;
}

.middle_search_box{
  width: 700px;
  height: 97.2px;
  display: flex;
  align-items: center;
}

.right_menuitems_container{
  width: 385px;
  display: flex;
  align-items: center;
  gap: 20px;
}

</style>