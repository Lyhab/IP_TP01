<template>
  <div :class="{ selected: isSelected }" class="picture_list_container" @click="handlePictureClick">
    <div class="picture_wrapper">
      <img :src="picture_list" class="picture_list" />
    </div>
  </div>
</template>

<script>
export default {
  props: ["picture_list", "is_selected"],
  computed: {
    isSelected() {
      return this.is_selected;
    },
  },
  methods: {
    handlePictureClick() {
      this.$emit("pictureClicked");
    },
  },
};
</script>

<style scoped>
.picture_list_container {
  width: 100%;
  height: 104px;
  overflow: hidden;
  cursor: pointer;
  box-sizing: border-box;
  border-radius: 15px;
  padding: 10px;
  border: 1px solid lightgray;
}

.picture_list_container.selected {
  border-color: #3BB77E;
}

.picture_wrapper {
  width: 100%;
  height: 100%;
  box-sizing: border-box;
  overflow: hidden;
}

.picture_list {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
