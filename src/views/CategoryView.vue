<template>

  <div class="container">
    <div class="productview_container">
        <div class="letter_container">
            <div class="title">Cake & Milk</div>
            <div class="desc">Home <i class="uil uil-angle-right-b"></i> Categories <i class="uil uil-angle-right-b"></i> Cake & Milk</div>
        </div>

        <img src='../assets/images/12Asset 1@4022244422x 2.png' class="img_background_left"/>
        <img src='../assets/images/12Asset 1@4022244422x 1.png' class="img_background_right"/>
    </div>
  </div>
    
</template>
  
<script>

</script>

<style scoped>
@import "https://unicons.iconscout.com/release/v4.0.8/css/line.css";
@import url('https://fonts.googleapis.com/css2?family=Knewave&family=Montserrat:wght@400;700&family=Quicksand:wght@600&family=Silkscreen:wght@400;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Knewave&family=Lato&family=Montserrat:wght@400;700&family=Quicksand:wght@600&family=Silkscreen:wght@400;700&display=swap');


.container{
  display: flex;
  justify-content: center;
  margin-top: 3vh;
}
.productview_container{
    width: 1384px;
    height: 235px;
    background-color: rgba(59, 183, 126, 0.2);
    position: relative;
    border-radius: 30px;
    overflow: hidden;
}

.letter_container{
    display: flex;
    height: 235px;
    flex-direction: column;
    position: relative;
    gap: 30px;
    z-index: 2;
    left: 8vh;
    justify-content: center;
}

.title{
    width: 727px;
    font-family: quicksand;
    font-size: 48px;
    font-weight: 700;
    color: rgba(37, 61, 78, 1);
}

.desc{
    width: 727px;
    font-family: Lato;
    font-size: 18px;
    font-weight: 400;
    color: rgba(126, 126, 126, 1);
    display: flex;
    align-items: center;
    gap: 10px;
}

.img_background_left{
    position: absolute;
    top: 0 ;
    left: -40px;
    z-index: 1;
}

.img_background_right{
    position: absolute;
    top: 0 ;
    right: -160px;
    z-index: 1;
}
</style>