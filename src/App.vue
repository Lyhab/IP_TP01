<template>
  <div class="all_container">

    <MenuOpt title="Featured Categories"/>

    <div class="category_container">
      <Categories v-for="category in store.categories" :title="category.name" :image="category.image" :bg_color="category.color" :amount="category.amount"></Categories>
    </div>

    <div class="promotion_container">
      <Promotions v-for="promotion in store.promotions" :letter="promotion.letter" :image="promotion.image" :bg_color="promotion.bg_color" :button_color="promotion.button_color" :button_bg_color="promotion.button_bg_color" :text="promotion.text"></Promotions>
    </div>

    <MenuOpt title="Popular Products" />
    
    <div class="product_container">
      <ProductCard v-for="product in store.products" :image="product.image" :bg_color="product.bg_color" :inform_bg_color="product.inform_bg_color" :inform_text="product.inform_text" :inform_color="product.inform_color" :company_name="product.company_name" :company_color="product.company_color" :title="product.title" :title_color="product.title_color" :rating="product.rating" :rating_color="product.rating_color" :weight="product.weight" :weight_color="product.weight_color" :discount_price="product.discount_price" :discount_color="product.discount_color" :price_original="product.price_original" :price_color="product.price_color" :add_bg="product.add_bg" :add_letter="product.add_letter" :add_color="product.add_color"></ProductCard>
    </div>
    
  </div>
</template>

<script>
import { useStore } from './stores/store'
import Categories from './components/category.vue'
import Promotions from './components/promotion.vue'
import ProductCard from './components/ProductCard.vue'
import MenuOpt from './components/MenuOpt.vue'

export default {
  name: "App",
  components: {
    Categories,
    Promotions,
    ProductCard,
    MenuOpt,
  },
  setup() {
    const store = useStore();
    return { store };
  },
};
</script>

<style>
@import "https://unicons.iconscout.com/release/v4.0.8/css/line.css";
@import url('https://fonts.googleapis.com/css2?family=Knewave&family=Montserrat:wght@400;700&family=Quicksand:wght@600&family=Silkscreen:wght@400;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Knewave&family=Lato&family=Montserrat:wght@400;700&family=Quicksand:wght@600&family=Silkscreen:wght@400;700&display=swap');


.all_container{
  width: 1586px;
  height: 140vh;
  display: flex;
  flex-direction: column;
  gap: 75px;
}

.menu_container{
    width: auto;
    height: 6vh;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.title_top{
    font-family: quicksand;
    font-weight: 700;
    font-size: 32px;
}

.category_container{
  width: 1586px;
  height: 185px;
  display: flex;
  gap: 25px;
}

.promotion_container{
  display: flex;
  gap: 24px;
}

.product_container {
  height: auto;
  display: flex;
  flex-wrap: wrap;
  gap: 24px;
  justify-content: space-between;
}

.product_card {
  flex-basis: calc(50% - 12px);
}

</style>
