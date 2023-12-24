<template>

    <div class="all_container">
        <div class="top_container">
            <router-link :to="`/`"  class="home_letter">Home</router-link>
            <i class="uil uil-angle-right-b" style="color: rgba(126, 126, 126, 1);"></i>
            <p class="route">{{ route }}</p>
        </div>

        <div class="mid_container">
            <div class="picture_description_display">
                <div class="left_display">
                    <div class="picture_wrapper">
                        <img :src="picture_display" class="picture_display" />
                    </div>
                </div>
                

                <div class="right_display">
                    <div class="instock">In Stock</div>

                    <ProductTitle :title="selectedTitle"></ProductTitle>

                    <Rating :rating="selectedRating"></Rating>

                    <ProductPrice :origin_price="SelectedOriginalPrice" :dis_price="SelectedDiscountPrice"></ProductPrice>

                    <p class="sum_desc">{{ sum_desc }}</p>

                    <div class="order_container">
                        <div class="amount_container">
                            <input v-model.number="amount" class="amount" :style="{ color: '#3BB77E' }" @change="validateAmount" />
                            <div class="add_minus_button">
                                <div @click="increaseamount">&#65087;</div>
                                <div @click="decreaseamount">&#65088;</div>
                            </div>
                        </div>

                        <div class="add_to_cart">
                            <i class="uil uil-shopping-cart-alt"></i>
                            Add to Cart
                        </div>

                        <div class="interest">
                            <i class="uil uil-heart"></i>
                        </div>
                        <div class="share">
                            <i class="uil uil-arrow-random"></i>
                        </div>
                    </div>

                    <ProductSource :vendor="SelectedVendor" :sku="SelectedSKU"></ProductSource>
                </div>
            </div>


            <div class="picture_option">
                <div class="arrow_button_container">
                    <button class="arrow" @click="moveLeft"><i class="uil uil-angle-left-b"></i></button>
                </div>
                <div class="picture_list_container">
                    <div class="picture_list_wrapper">
                        <PictureList
                            v-for="(picturelist, index) in store.picturelists"
                            :key="picturelist.id"
                            :picture_list="picturelist.picture_list"
                            @pictureClicked="handlePictureClick(index)"
                            :is_selected="index === selectedImageIndex"
                        ></PictureList>
                    </div>
                </div>
                <div class="arrow_button_container">
                    <button class="arrow" @click="moveRight"><i class="uil uil-angle-right-b"></i></button>
                </div>
            </div>
        </div>
        

        <div class="bot_container">
            <div class="top_tab">
                <button class="top_desc">Description</button>
                <button class="add_info">Additional Info</button>
                <button class="reviews">Review (<ReviewAmount :review_amount="selectedReview_amount"></ReviewAmount>)</button>
            </div>

            <ProductDescription :description="selectedDescription"></ProductDescription>
        </div>
    </div>

</template>


<script>
import { useStore } from '../stores/store'
import PictureList from './PictureList.vue'
import ProductDescription from './ProductDescription.vue'
import ReviewAmount from './ReviewAmount.vue';
import ProductTitle from './ProductTitle.vue';
import Rating from './ProductRating.vue'
import ProductPrice from './ProductPrice.vue'
import ProductSource from './ProductSource.vue';


export default{
    components: {
    PictureList,
    ProductDescription,
    ReviewAmount,
    ProductTitle,
    Rating,
    ProductPrice,
    ProductSource,
    },
    setup() {
        const store = useStore();
        return { store };
    },
    computed: {
        sum_desc() {
            if (this.selectedDescription) {
                const regex = /<p>(.*?)<\/p>/;
                const match = this.selectedDescription.match(regex);

                return match ? match[1] : "";
            }

            return "";
        },
    },
    data() {
        return {
            amount: 1,
            route: '',
            picture_display: this.store.picturelists.length > 0 ? this.store.picturelists[0].picture_list : null,
            selectedImageIndex: 0,
            selectedDescription: '',
            selectedReview_amount: '',
            selectedTitle: '',
            selectedRating: '',
            SelectedOriginalPrice: '',
            SelectedDiscountPrice: '',
            SelectedVendor: '',
            SelectedSKU: '',
        };
    },
    
    methods: {
        validateAmount() {
            if (this.amount < 1) {
                this.amount = 1;
            } else if (this.amount > 99) {
                this.amount = 99;
            }
            this.amount = Math.min(Math.max(1, this.amount), 99);
        },
        increaseamount() {
            if (this.amount < 99) {
                this.amount++;
            }
        },
        decreaseamount() {
            if (this.amount > 1) {
                this.amount--;
            }
        },
        updateCurrentImage(index) {
            this.selectedImageIndex = index;
        },
        handlePictureClick(index) {
            const pictureListUrl = this.store.picturelists[index].picture_list;
            const descriptionId = this.store.picturelists[index].id;
            const review_amountId = this.store.picturelists[index].id;
            const titleId = this.store.picturelists[index].id;
            const ratingId = this.store.picturelists[index].id;
            const originalpriceId = this.store.picturelists[index].id;
            const discountpriceId = this.store.picturelists[index].id;
            const vendorId = this.store.picturelists[index].id;
            const skuId = this.store.picturelists[index].id;
            this.updatePictureDisplay(pictureListUrl, index);
            this.updateDescription(descriptionId);
            this.updateReviewAmount(review_amountId);
            this.updateTitle(titleId);
            this.updateRating(ratingId);
            this.updateOriginalPrice(originalpriceId);
            this.updateDiscountPrice(discountpriceId);
            this.updateVendor(vendorId);
            this.updateSKU(skuId);
        },
        updatePictureDisplay(pictureListUrl, selectedIndex) {
            this.picture_display = pictureListUrl;
            this.updateCurrentImage(selectedIndex);
            this.$emit('pictureSelected', selectedIndex);
        },
        updateDescription(descriptionId) {
            const selectedDescription = this.store.productdescriptions.find(desc => desc.id === descriptionId);
            if (selectedDescription) {
                this.selectedDescription = selectedDescription.description;
            }
        },
        updateReviewAmount(review_amountId){
            const selectedReview_amount = this.store.reviewamounts.find(revam => revam.id === review_amountId);
            if (selectedReview_amount) {
                this.selectedReview_amount = selectedReview_amount.review_amount;
            }
        },
        updateTitle(titleId) {
            const selectedTitle = this.store.producttitles.find(title => title.id === titleId);
            if (selectedTitle) {
                this.selectedTitle = selectedTitle.title;
                this.updateRouteFromTitle();
                console.log('updateRouteFromTitle called');
            }
        },
        updateRouteFromTitle() {
            if (this.selectedTitle !== null) {
                const words = this.selectedTitle.split(' ');
                this.route = words.slice(0, 4).join(' ');
            } else {
                this.route = '';
            }
        },
        updateRating(ratingId){
            const selectedRating = this.store.ratings.find(rating => rating.id === ratingId);
            if (selectedRating) {
                this.selectedRating = selectedRating.rating;
            }
        },
        updateOriginalPrice(originalpriceId){
            const SelectedOriginalPrice = this.store.productprices.find(originalprice => originalprice.id === originalpriceId);
            if (SelectedOriginalPrice) {
                this.SelectedOriginalPrice = SelectedOriginalPrice.origin_price;
            }
        },
        updateDiscountPrice(discountpriceId){
            const SelectedDiscountPrice = this.store.productprices.find(discountprice => discountprice.id === discountpriceId);
            if (SelectedDiscountPrice) {
                this.SelectedDiscountPrice = SelectedDiscountPrice.dis_price;
            }
        },
        updateVendor(vendorId){
            const SelectedVendor = this.store.productsources.find(vendor => vendor.id === vendorId);
            if (SelectedVendor) {
                this.SelectedVendor = SelectedVendor.vendor;
            }
        },
        updateSKU(skuId){
            const SelectedSKU = this.store.productsources.find(sku => sku.id === skuId);
            if (SelectedSKU) {
                this.SelectedSKU = SelectedSKU.sku;
            }
        },
        updateAll() {
            const pictureListUrl = this.store.picturelists[this.selectedImageIndex].picture_list;
            const descriptionId = this.store.picturelists[this.selectedImageIndex].id;
            const review_amountId = this.store.picturelists[this.selectedImageIndex].id;
            const titleId = this.store.picturelists[this.selectedImageIndex].id;  
            const ratingId = this.store.picturelists[this.selectedImageIndex].id;  
            const originalpriceId = this.store.picturelists[this.selectedImageIndex].id; 
            const discountpriceId = this.store.picturelists[this.selectedImageIndex].id; 
            const vendorId = this.store.picturelists[this.selectedImageIndex].id;  
            const skuId = this.store.picturelists[this.selectedImageIndex].id;  
            this.updatePictureDisplay(pictureListUrl, this.selectedImageIndex);
            this.updateDescription(descriptionId);
            this.updateReviewAmount(review_amountId);
            this.updateTitle(titleId);
            this.updateRating(ratingId);
            this.updateOriginalPrice(originalpriceId);
            this.updateDiscountPrice(discountpriceId);
            this.updateVendor(vendorId);
            this.updateSKU(skuId);
        },
        moveLeft() {
            if (this.store.picturelists.length === 0) return;

            if (this.selectedImageIndex > 0) {
                this.updateCurrentImage(this.selectedImageIndex - 1);
            } else {
                this.updateCurrentImage(this.store.picturelists.length - 1);
            }

            this.updateAll();
        },
        moveRight() {
            if (this.store.picturelists.length === 0) return;

            if (this.selectedImageIndex < this.store.picturelists.length - 1) {
                this.updateCurrentImage(this.selectedImageIndex + 1);
            } else {
                this.updateCurrentImage(0);
            }

            this.updateAll();
        },
    },
    mounted() {
        if (this.store.picturelists.length > 0) {
            this.updateCurrentImage(0);
            this.updatePictureDisplay(this.store.picturelists[0].picture_list, 0);
            this.updateDescription(this.store.picturelists[0].id);
            this.updateReviewAmount(this.store.picturelists[0].id);
            this.updateTitle(this.store.producttitles[0].id);
            this.updateRating(this.store.producttitles[0].id);
            this.updateOriginalPrice(this.store.producttitles[0].id);
            this.updateDiscountPrice(this.store.producttitles[0].id);
            this.updateVendor(this.store.producttitles[0].id);
            this.updateSKU(this.store.producttitles[0].id);
        }
    },
};

</script>


<style scoped>

.all_container{
    display: flex;
    flex-direction: column;
    align-items: center;
}

.top_container{
    width: 1400px;
    background-color: white;
    display: flex;
    align-items: center;
    margin-top: 10px;
    font-size: 18px;
    font-family: Lato;
    font-weight: 400;
    gap: 15px;
}

.home_letter{
    color: rgba(126, 126, 126, 1);
}

.route{
    color: #3BB77E;
}

.mid_container{
    width: 1400px;
    background-color: white;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.picture_description_display{
    display: flex;
    gap: 20px;
}

.left_display{
    width: 770px;
    height: 490px;
    overflow: hidden;
    cursor: pointer;
}

.picture_wrapper {
    width: 100%;
    height: 100%;
    box-sizing: border-box;
    border: 1px solid lightgray;
    border-radius: 15px;
    overflow: hidden;
    padding: 10px;
}

.picture_display {
    width: 100%;
    height: 100%;
    object-fit: contain;
    max-width: 850px;
    max-height: 700px;
}

.right_display{
    width: 610px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    cursor: pointer;
}

.instock{
    width: 80px;
    font-family: Quicksand;
    font-weight: 700;
    background-color: #DEF9EC;
    color: #3BB77E;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 10px;
    gap: 15px;
    font-weight: 700;
    border-radius: 7px;
}

.sum_desc{
    font-family: Lato;
    font-weight: 400;
    font-size: 16px;
    color: #7E7E7E;
}

.order_container{
    display: flex;
    gap: 20px;
}

.amount_container{
    width: 100px;
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    color: #3BB77E;
    font-weight: 700;
    border: 1px solid #3BB77E;
    border-radius: 7px;
}

.amount{
    width: 15px;
    font-family: Quicksand;
    margin-left: 30px;
}

.add_minus_button{
    display: flex;
    flex-direction: column;
    gap: 6px;
    cursor: pointer;
    margin-right: 10px;
}

.add_to_cart{
    font-family: Quicksand;
    font-weight: 700;
    background-color: #3BB77E;
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 10px;
    gap: 15px;
    font-weight: 700;
    border-radius: 7px;
}

.interest, .share{
    color: lightgray;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 10px;
    gap: 15px;
    border: 1px solid lightgray;
    border-radius: 7px;
}

.picture_option{
    width: 55%;
    height: 120px;
    
    display: flex;
    gap: 15px;
    margin-top: 10px;
}

.picture_list_container {
    overflow-y: auto;
    display: flex;
    gap: 20px;
    flex-wrap: nowrap;
}

.picture_list_wrapper {
  display: flex;
  gap: 20px;
  flex-shrink: 0;
}

.arrow_button_container {
  display: flex;
  align-items: center;
}

.arrow {
  font-size: 20px;
}

.bot_container{
    width: 1400px;
    margin-top: 10px;
    height: 300px;
    background-color: white;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
    border: 1px solid lightgray;
    border-radius: 15px;
}

.top_tab{
    width: 90%;
    margin-top: 50px;
    display: flex;
    gap: 25px;
}

.top_desc{
    color: rgba(59, 183, 126, 1);
    border: 1px solid rgba(59, 183, 126, 1);
}

.reviews {
  display: flex;
  align-items: center;
}

button{
    padding-left: 20px;
    padding-right: 20px;
    padding-top: 10px;
    padding-bottom: 10px;
    color: rgba(182, 182, 182, 1);
    background-color: white;
    border: 1px solid lightgray;
    border-radius: 50px;
    font-family: Quicksand;
    font-size: 16px;
    font-weight: 700;
    box-shadow: 3px 3px 5px lightgray;
    cursor: pointer;
}

input{
    border: none;
}
</style>