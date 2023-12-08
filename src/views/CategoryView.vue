<template>

    <div class="overall_container">
  
      Hello
  
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
  
  .overall_container{
    width: 1786px;
    height: 202vh;
    display: flex;
    background-color: white;
    padding-left: 100px;

  }
  
  .all_container{
    width: 1586px;
    height: 140vh;
    display: flex;
    flex-direction: column;
    gap: 75px;
  }
  
  .headers_container{
    display: flex;
    flex-direction: column;
    gap: 2vh;
  }
  
  .header_container{
    display: flex;
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