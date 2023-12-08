<template>
  <div class="container">
    <HeaderLayout/>
    <RouterView/>
  </div>
</template>

<script>
import { useStore } from '../src/stores/store'
import {RouterLink, RouterView} from "vue-router";
import HeaderLayout from "../src/components/HeaderLayout.vue";

export default {
  name: "App",
  components: {
    HeaderLayout,
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
}
</style>
