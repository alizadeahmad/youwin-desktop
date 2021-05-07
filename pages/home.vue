<template>
    <div class="">

        <div class="row">
            <div class="col-3 px-3">
                <div class="categories">
                    <div class="categories-header px-1 py-2">
                        <img class="vam" src="/images/home/icon1.png" width="26">
                        <span class="fs-12">دسته بندی کالاها</span>
                    </div>
                    <div class="categories-wrapper">
                        <ul>
                            <li v-for="i in 9">
                                <nuxt-link to="/categories">
                                    <img class="vam" src="/images/category/1.png">
                                    <span class="fs-13 accent--text">شیر و فراورده های لبنی</span>
                                </nuxt-link>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
            <div class="col-9">
                <div class="slider-default">
                    <div class="swiper-wrapper">
                        <SwiperSlideHome v-for="i in 5"
                            :key="i"
                            link="/"
                            title="12"
                            className="br-15"
                            image="/images/home/slide1.png" />
                    </div>
                </div>
            </div>
        </div>
  
        <div class="row ofh">
            <div class="products-box mt-8">
                <div class="darkGray--text mb-2 mx-2">پیشنهاد روز</div>
                <div class="swiper-wrapper">
                    <SwiperSlideProductDesktop v-for="i in 10"
                        :key="i"
                        :id="i"
                        name="گوشت چرخ کرده مهیا"
                        priceDiscount="320000"
                        price="300000"
                        image="/images/home/product.png" />
                </div>
            </div>
        </div>

        <div class="row app-area my-10">
            <div class="col-12 text-center">
                <img src="/images/home/da.png">
            </div>
            <div class="app-area-dls">
                <a href="#"><img class="app-area-dl" src="/images/home/da1.png"></a>
                <a href="#"><img class="app-area-dl" src="/images/home/da2.png"></a>
                <a href="#"><img class="app-area-dl" src="/images/home/da3.png"></a>
            </div>
        </div>

        <div class="row ofh">
            <div class="products-box mt-8">
                <div class="darkGray--text mb-2 mx-2">پر تخفیف ترین ها</div>
                <div class="swiper-wrapper">
                    <SwiperSlideProductDesktop v-for="i in 10"
                        :key="i"
                        :id="i"
                        name="گوشت چرخ کرده مهیا"
                        priceDiscount="320000"
                        price="300000"
                        image="/images/home/product.png" />
                </div>
            </div>
        </div>

        <div class="row my-4 ofh">
            <div class="products-box mt-8">
                <div class="darkGray--text mb-2 mx-2">جدیدترین ها</div>
                <div class="swiper-wrapper">
                    <SwiperSlideProductDesktop v-for="i in 10"
                        :key="i"
                        :id="i"
                        name="گوشت چرخ کرده مهیا"
                        priceDiscount="320000"
                        price="300000"
                        image="/images/home/product.png" />
                </div>
            </div>
        </div>


    </div>
</template>

<script>
import Swiper from 'swiper';
import 'swiper/css/swiper.css';
export default {
    layout: 'home',
    mounted(){
        this.$store.commit('_HOME', ['wmenu', 0]);
        new Swiper('.slider-default', {
            /*
            navigation: {
                nextEl: '.swiper-button-next',
                prevEl: '.swiper-button-prev',
            },
            */
            autoplay: {
                delay: 3000,
            }
        });
        new Swiper('.products-box', {
            slidesPerView: 'auto',
            spaceBetween: 25,
        });
    },
    data(){
        return{
            modalAddress: false,
            address:{
                name: 'خونه',
                address: 'یزد امام شهر، انتهای بلوار کارگر',
            },
        }
    },
    methods:{
        closeModalAddress(){
            this.modalAddress = false;
        },
    },
    computed:{
        selectedShop(){
            return this.$store.state._home.selectedShop;
        }
    }
};
</script>

<style>
.vam{
    vertical-align: middle;
}
.categories{
    background-color: #fff;
    box-shadow: 0 2px 15px -5px rgb(0,0,0,.20);
    border-radius: 5px;
}
.categories .categories-header{
    background-color: #f2f2f2;
}
.categories ul{
    list-style: none;
    margin: 0;
    padding: 0;
}
.categories li{
    border-bottom: 1px solid #eee;
}
.categories a{
    padding: 6px;
    display: block;
    text-decoration: none;
}
.slider-default{
    overflow: hidden;
}
.app-area{
    /*background-color: rgb(248,248,247);*/
}
.app-area-dls{
    position: absolute;
    margin-top: 230px;
    right: calc(50% - 500px);
}
.app-area-dl{
    display: block;
    margin-top: 14px;
    border-radius: 6px;
}



.deactive{
    opacity: 0;
}
.addresses{
    border: 1px solid lightgray;
    border-radius: 10px;
    padding: 15px 10px;
    margin-bottom: 10px;
}
</style>