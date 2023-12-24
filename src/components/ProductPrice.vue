<template>
    <div class="price_container">
      <div class="discounted_price">${{ dis_price }}</div>
      <div class="original_price">${{ origin_price }}</div>
    </div>
  </template>
  
  <script>
  export default {
    props: ["dis_price", "origin_price"],
  };
  </script>
  
  <style scoped>
  .price_container {
    display: flex;
    font-family: Quicksand;
    font-weight: 700;
    gap: 15px;
  }
  
  .discounted_price {
    font-size: 60px;
    color: #3BB77E;
  }
  
  .original_price {
    margin-top: 30px;
    font-size: 30px;
    color: #B6B6B6;
    text-decoration: line-through;
  }
  </style>
  