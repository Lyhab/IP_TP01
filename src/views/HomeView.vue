<template>

  <div class="overall_container">

    <div class="all_container">

      <div class="sub_container">
        <div class="subscribe_container">
          <Subscribe v-for="subscribe in store.subscribes" :image_background="subscribe.image_background" :image_frontground="subscribe.image_frontground" :title_letter="subscribe.title_letter" :title_letter_color="subscribe.title_letter_color" :desc_letter="subscribe.desc_letter" :desc_letter_color="subscribe.desc_letter_color"></Subscribe>
        </div>
      </div>

      <Menu v-for="menu in store.menus.filter(item => item.id === 1)" :key="menu.id" :title="menu.title" :title_color="menu.title_color"/>

      <div class="category_container">
        <Categories v-for="category in store.categories" :title="category.name" :image="category.image" :bg_color="category.color" :amount="category.amount"></Categories>
      </div>

      <div class="promotion_container">
        <Promotions v-for="promotion in store.promotions" :letter="promotion.letter" :image="promotion.image" :bg_color="promotion.bg_color" :button_color="promotion.button_color" :button_bg_color="promotion.button_bg_color" :text="promotion.text"></Promotions>
      </div>

      <Menu v-for="menu in store.menus.filter(item => item.id === 2)" :key="menu.id" :title="menu.title" :title_color="menu.title_color"/>

      <div class="product_container">
        <ProductCard v-for="product in store.products" :image="product.image" :bg_color="product.bg_color" :inform_bg_color="product.inform_bg_color" :inform_text="product.inform_text" :inform_color="product.inform_color" :company_name="product.company_name" :company_color="product.company_color" :title="product.title" :title_color="product.title_color" :rating="product.rating" :rating_color="product.rating_color" :weight="product.weight" :weight_color="product.weight_color" :discount_price="product.discount_price" :discount_color="product.discount_color" :price_original="product.price_original" :price_color="product.price_color" :add_bg="product.add_bg" :add_letter="product.add_letter" :add_color="product.add_color"></ProductCard>
      </div>

    </div>

  </div>

</template>
  
<script>
import { useStore } from '../stores/store'
import Categories from '../components/category.vue'
import Promotions from '../components/promotion.vue'
import ProductCard from '../components/ProductCard.vue'
import Menu from '../components/Menu.vue'
import Menuitem from '../components/menuitem.vue'
import Searchbox from '../components/SearchBox.vue'
import Header from '../components/Header.vue'
import SubHeader from '../components/SubHeader.vue'
import Subscribe from '../components/Subscribe.vue'
import HeaderLayout from '../components/HeaderLayout.vue'

export default {
  name: "HomeView",
  components: {
    Categories,
    Promotions,
    ProductCard,
    Menu,
    Menuitem,
    Searchbox,
    Header,
    SubHeader,
    Subscribe,
    HeaderLayout,
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

.overall_container{
  width: 100%;
  display: flex;
  margin-top: 20px;
  justify-content: center;
}

.all_container{
  width: 100%;
  height: 140vh;
  display: flex;
  flex-direction: column;
  gap: 75px;
}

.subscribe_container{
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 2vh;
}

.sub_container{
  width: 100%;
  display: flex;
  justify-content: center;
}

.category_container{
  width: 100%;
  height: 185px;
  display: flex;
  gap: 25px;
}

.promotion_container{
  width: 100%;
  display: flex;
  gap: 30px;
}

.product_container {
  height: auto;
  display: grid;
  grid-template-columns: 298px 298px 298px 298px;
  row-gap: 45px;
  column-gap: 93px;
}
</style>