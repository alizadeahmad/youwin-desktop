<template>
    <div class="">

        <div class="row breadcrumbs">
            <div class="col-9">
                <v-breadcrumbs :items="items"></v-breadcrumbs>
            </div>
            <div class="col-3 row text-left">
                <div class="col">
                    <div class="a-select-wrapper mb-6">
                        <!-- <label>مرتب سازی</label> -->
                        <select>
                            <option disabled="" selected="">مرتب سازی</option>
                            <option>جدیدترین</option>
                            <option>ارزان ترین</option>
                        </select>
                        <i class="material-icons">keyboard_arrow_down</i>
                    </div>
                </div>
                <div class="col" style="max-width:46px;">
                    <v-btn
                      class="filter-btn"
                      large
                      color="white"
                    >
                      <v-icon dark>
                        filter_alt
                      </v-icon>
                    </v-btn>
                </div>
            </div>
        </div>


        <div class="bs-cb">
            <SwiperSlideProductDesktop v-for="i in 15"
                :key="i"
                :id="i"
                name="گوشت چرخ کرده مهیا"
                priceDiscount="320000"
                price="300000"
                image="/images/home/product.png" />
        </div>
        


    </div>
</template>

<script>
import Swiper from 'swiper';
import 'swiper/css/swiper.css';
export default {
    layout: 'home',
    mounted(){
        /*
        this.$store.commit('_HOME', ['wmenu', 0]);
        new Swiper('.products-box', {
            slidesPerView: 'auto',
            spaceBetween: 25,
        });
        */
    },
    data(){
        return{
            items: [
                {text: 'دسته بندی ها', disabled: true, href: '/'},
                {text: 'شیر و فراورده های لبنی', disabled: false, href: '/'},
            ],
            category: 'شیر و فراورده های لبنی'
        }
    },
    methods:{
    },
    computed:{
    }
};
</script>

<style>
.bs-cb{
    box-sizing: content-box;
}
.breadcrumbs a{
    color: #373e48;
}
.swiper-slide{
    display: inline-block;
    margin: 10px !important;
}
.filter-btn{
    width: 46px !important;
    min-width: 46px !important;
    height: 46px !important;
    min-height: 46px !important;
}
</style>