<template>
    <div class="source_container">
        <div class="vendor">Vendor: <div class="vendor_name">{{ vendor }}</div></div>
        <div class="sku">SKU: <div class="sku_code">{{ sku }}</div></div>
    </div>
</template>

<script>
  export default {
    props: ["vendor", "sku"],
  };
</script>

<style scoped>
.source_container{
  display: flex;
  flex-direction: column;
  gap: 10px;
  font-family: Lato;
  font-size: 14px;
  font-weight: 400;
}

.vendor{
  display: flex;
  gap: 10px;
}

.vendor_name{
  color: #B6B6B6;
}

.sku{
  display: flex;
  gap: 10px;
}

.sku_code{
  color: #B6B6B6;
}
</style>