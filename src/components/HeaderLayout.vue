<template>
    <div class="header_container">
        <Header></Header>
    </div>

    <div class="subheader_container">
        <SubHeader v-for="subheader in store.subheaders" :browse_left_icon="subheader.browse_left_icon" :browse_left_icon_color="subheader.browse_left_icon_color" :browse_left_icon_size="subheader.browse_left_icon_size" :browse_text_color="subheader.browse_text_color" :browse_text="subheader.browse_text" :browse_right_icon="subheader.browse_right_icon" :browse_right_icon_color="subheader.browse_right_icon_color" :browse_right_icon_size="subheader.browse_right_icon_size" :right_icon="subheader.right_icon" :right_icon_color="subheader.right_icon_color" :right_icon_size="subheader.right_icon_size" :tel="subheader.tel" :tel_color="subheader.tel_color" :tel_size="subheader.tel_size"></SubHeader>
    </div>
</template>

<script>
import { useStore } from '../stores/store'
import Header from '../components/Header.vue'
import SubHeader from '../components/SubHeader.vue'

export default {
  name: "HeaderLayout",
  components: {
    Header,
    SubHeader,
  },
  setup() {
    const store = useStore();
    return { store };
  },
};
</script>

<style scoped>

</style>