<template>
    <div class="rating">
      <div class="stars">
        <template v-for="i in 5">
          <span span :class="{ 'star-gray': i > rating, 'star-yellow': i <= rating }">&#9733;</span>
        </template>
      </div>
      <div class="rating_number">({{ rating }}.0)</div>
    </div>
  </template>
  
  <script>
  export default {
    props: ["rating"],
  };
  </script>
  
  <style scoped>
  .rating {
    margin-top: 10px;
    display: flex;
    align-items: center;
    gap: 6px;
  }
  
  .stars {
    color: #CDCDCD;
    font-size: 14px;
  }
  
  .star-yellow,
  .star-gray {
    font-size: 1.5em;
    margin: 0 2px;
    display: inline-block;
  }
  
  .star-yellow {
    color: #FDC040;
    border-radius: 50%;
  }

  .rating_number{
    font-family: Lato;
    font-weight: 400;
    font-size: 16px;
    color: #7E7E7E;
  }
  </style>
  