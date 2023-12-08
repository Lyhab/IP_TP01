<template>
    <div class="Products" :style="{backgroundColor:bg_color}">
        <div class="inform_container">
            <div class="inform" :style="{color:inform_color, backgroundColor:inform_bg_color}">{{ inform_text }}</div>
        </div>

        <div class="image_container">
            <img :src='image' class="img"/>
        </div>

        <div class="company" :style="{color:company_color}">{{ company_name }}</div>

        <div class="title" :style="{color:title_color}">{{ title }}</div>

        <div class="rating_container">
            <i class="uil uil-star"></i>
            <i class="uil uil-star"></i>
            <i class="uil uil-star"></i>
            <i class="uil uil-star"></i>
            <i class="uil uil-star"></i>

            <div class="rating" :style="{color:rating_color}">({{ rating }}.0)</div>
        </div>

        <div class="weight" :style="{color:weight_color}">{{ weight }}</div>

        <div class="bottom_container">
            <div class="left_container">
                <div class="discount" :style="{color:discount_color}">
                    <i class="uil uil-dollar-alt"></i>
                    <div class="discount_price">{{ discount_price }}</div>
                </div>

                <div class="price" :style="{color:price_color}">
                    <i class="uil uil-dollar-alt" style="text-decoration: line-through;"></i>
                    <div class="price_original">{{ price_original }}</div>
                </div>
            </div>

            <div class="right_container">
                <div class="add_container" :style="{color:add_color, backgroundColor:add_bg}">
                    <div class="add_letter">{{ add_letter }}</div>
                    <i class="uil uil-plus"></i>
                </div>
            </div>
        </div>
    </div>

</template>

<script>

export default{
    props: ["bg_color", "image",
    "inform_bg_color", "inform_text", "inform_color", 
    "company_name", "company_color", 
    "title", "title_color",
    "rating", "rating_color",
    "weight", "weight_color",
    "discount_price", "discount_color",
    "price_original", "price_color",
    "add_bg", "add_letter", "add_color"
    ],

};
</script>


<style scoped>
@import "https://unicons.iconscout.com/release/v4.0.8/css/line.css";
@import url('https://fonts.googleapis.com/css2?family=Knewave&family=Montserrat:wght@400;700&family=Quicksand:wght@600&family=Silkscreen:wght@400;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Knewave&family=Lato&family=Montserrat:wght@400;700&family=Quicksand:wght@600&family=Silkscreen:wght@400;700&display=swap');

.Products{
    width: 298px;
    height: 402px;
    border: 2px solid lightgray;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    padding: 19px;
}

.inform_container{
    height: 50px;
    position: relative;
    margin-left: -19px;
    margin-top: -15px;
    z-index: 1;
}

.inform{
    width: 58px;
    height: 32px;
    position: absolute;
    bottom: 0;
    border-top-right-radius: 100px;
    border-bottom-right-radius: 100px;
    font-size: 12px;
    font-weight: 400;
    font-family: Lato;
    display: flex;
    align-items: center;
    justify-content: center;
}

.image_container{
    width: 100%;
    height: 190px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.img{
    z-index: 0;
    bottom: 0;
    right: 0;
    border-radius: 10px;
}

.company{
    width: 100%;
    height: 26px;
    font-size: 12px;
    font-weight: 400;
    font-family: Lato;
    display: flex;
    align-items: center;
}

.title{
    width: 100%;
    height: 35px;
    font-family: quicksand;
    font-size: 14px;
    font-weight: 700;
    display: flex;
    align-items: center;
}

.rating_container{
    width: 100%;
    height: 26px;
    display: flex;
    font-size: 12px;
    font-weight: 400;
    font-family: Lato;
    display: flex;
    align-items: center;
}

.rating{
    margin-left: 10px;
    display: flex;
    align-items: center;
}

.weight{
    width: 100%;
    height: 26px;
    font-size: 12px;
    font-weight: 400;
    font-family: Lato;
    display: flex;
    align-items: center;
}

.bottom_container{
    width: 100%;
    height: 49px;
    display: flex;
    margin-bottom: -12px;
}

.left_container{
    width: 50%;
    height: 100%;
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: quicksand;
    font-weight: 700;
}

.discount{ 
    display: flex;
    font-size: 20px;
    align-items: center;
    justify-content: center;
}

.price{
    display: flex;
    font-size: 16px;
    align-items: center;
    justify-content: center;
}

.price_original{
    text-decoration: line-through;
    padding-top: 1px;
}

.right_container{
    width: 50%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: end;
    font-family: quicksand;
    font-weight: 700;
}

.add_container{
    width: 67px;
    height: 29px;
    font-size: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 5px;
    margin-right: 1vh;
    border-radius: 6px;
}


</style>