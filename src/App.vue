<template>
  <div class="all_container">
    <div class="category_container">
      <Categories :image="Categories1"  bg_color="#F2FCE4" title="Burger" amount="14"/>
      <Categories :image="Categories2"  bg_color="#FFFCEB" title="Peach" amount="17"/>
      <Categories :image="Categories3"  bg_color="#ECFFEC" title="Organic Kiwi" amount="21"/>
      <Categories :image="Categories4"  bg_color="#FEEFEA" title="Red Apple" amount="68"/>
      <Categories :image="Categories5"  bg_color="#FFF3EB" title="Snack" amount="34"/>
      <Categories :image="Categories6"  bg_color="#FFF3FF" title="Black Plum" amount="25"/>
      <Categories :image="Categories7"  bg_color="#F2FCE4" title="Vegetables" amount="65"/>
      <Categories :image="Categories8"  bg_color="#FFFCEB" title="Headphone" amount="33"/>
      <Categories :image="Categories9"  bg_color="#F2FCE4" title="Cake & Milk" amount="54"/>
      <Categories :image="Categories10"  bg_color="#FFF3FF" title="Orange" amount="63"/>
    </div>
    <div class="promotion_container">
      <Promotions :image="Promotions1"  bg_color="#F0E8D5" letter="Everyday Fresh & Clean with Our Products" :buttonProps="Buttons1"/>
      <Promotions :image="Promotions2"  bg_color="#F3E8E8" letter="Make your Breakfast Healthy and Easy" :buttonProps="Buttons1"/>
      <Promotions :image="Promotions3"  bg_color="#E7EAF3" letter="The best Organic Products Online" :buttonProps="Buttons2"/>
    </div>
  </div>
</template>

<script>
import Categories from './components/category.vue'
import Promotions from './components/promotion.vue'

export default {
  name: "App",
  components: {
    Categories,
    Promotions,
  },
  data() {
    return {
      Categories1: new URL('./assets/images/cat-13 1.png', import.meta.url),
      Categories2: new URL('./assets/images/cat-11 1.png', import.meta.url),
      Categories3: new URL('./assets/images/cat-12 1.png', import.meta.url),
      Categories4: new URL('./assets/images/cat-9 1.png', import.meta.url),
      Categories5: new URL('./assets/images/cat-3 1.png', import.meta.url),
      Categories6: new URL('./assets/images/cat-4 1.png', import.meta.url),
      Categories7: new URL('./assets/images/cat-1 4.png', import.meta.url),
      Categories8: new URL('./assets/images/cat-15 1.png', import.meta.url),
      Categories9: new URL('./assets/images/cat-14 1.png', import.meta.url),
      Categories10: new URL('./assets/images/cat-7 1.png', import.meta.url),
      

      Promotions1: new URL('./assets/images/Cms-04 1.png', import.meta.url),
      Promotions2: new URL('./assets/images/Cat-01 1.png', import.meta.url),
      Promotions3: new URL('./assets/images/Cms-03 1.png', import.meta.url),


      Buttons1: { text: "Shop Now", color: "white", bg_color: "#3BB77E"},
      Buttons2: { text: "Shop Now", color: "white", bg_color: "#FDC040"}
    };
  }
};
</script>

<style>

.all_container{
  display: flex;
  flex-direction: column;
  gap: 75px;
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
</style>
