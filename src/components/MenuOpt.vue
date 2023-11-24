<template>
    <div class="menu">
    <div class="col1" :style="{color:title_color}">{{ title }}</div>
    <div class="col2">
      <ul>
        <li class="active">All</li>
        <li>Milks & Dairies</li>
        <li>Coffees & Teas</li>
        <li>Pet Foods</li>
        <li>Meats</li>
        <li>Vegetables</li>
        <li>Friuts</li>
      </ul>
    </div>
  </div>

</template>

<script>

export default{
    props: ["title", "title_color"],

};
</script>

<style scoped>
@import "https://unicons.iconscout.com/release/v4.0.8/css/line.css";
@import url('https://fonts.googleapis.com/css2?family=Knewave&family=Montserrat:wght@400;700&family=Quicksand:wght@600&family=Silkscreen:wght@400;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Knewave&family=Lato&family=Montserrat:wght@400;700&family=Quicksand:wght@600&family=Silkscreen:wght@400;700&display=swap');

.menu{
  
  top: 0px;
  left: 0px;
  display: flex;
  width: 100%;
  justify-content: space-between;
}
.col1{
  font-family: Quicksand;
  font-size: 32px;
}
.col2{
  bottom: 0;
  text-align: center;
  display: flex;
  align-items: center;

}
.active {
  font-weight: bold;
}
ul {
  list-style-type: none;  
  display: flex;
  font-family: Lato;
  font-size: 16px;
}
ul li {
  margin-right: 30px;
}

</style>