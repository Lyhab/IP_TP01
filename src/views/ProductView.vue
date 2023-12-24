<template>

    <div class="all_container">
        <ProductDisplay v-for="productdisplay in store.productdisplays" :route="productdisplay.route" :review_amount="productdisplay.review_amount"></ProductDisplay>
    </div>
    
</template>

<script>
import { useStore } from '../stores/store'
import ProductDisplay from '../components/ProductDisplay.vue'


export default{
    components: {
    ProductDisplay,
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
</style>