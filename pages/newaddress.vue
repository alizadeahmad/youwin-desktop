<template>
    <div class="">


        <div class="fs-14 fw-600 mt-6 mb-2">حساب کاربری من / آدرس های من / افزودن آدرس جدید</div>

        <div class="row">
            <div class="col products-box mt-8">

                <div class="row mt-8">
                    <div class="col-3"></div>
                    <div class="col-6">
                        <div class="row">
                            <div class="col a-select-wrapper">
                              <label>استان</label>
                              <select>
                                <option>-</option>
                                <option>تهران</option>
                                <option>یزد</option>
                              </select>
                              <i class="material-icons">keyboard_arrow_down</i>
                            </div>
                            <div class="col a-select-wrapper">
                              <label>شهرستان</label>
                              <select>
                                <option>-</option>
                              </select>
                              <i class="material-icons">keyboard_arrow_down</i>
                            </div>
                        </div>
                        <div class="row mt-4">
                            <div class="col-6"><a-input label="عنوان آدرس" required/></div>
                        </div>
                        <div class="row">
                            <div class="col"><a-input label="آدرس کامل" required/></div>
                        </div>
                        <div class="row">
                            <div class="col-12 fs-11">انتخاب آدرس روی نقشه</div>
                            <div class="col-12">
                                <img src="images/tmp/map.jpg">
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-8"></div>
                            <div class="col-4">
                                <v-btn @click="register" color="success" elevation="1" block x-large>
                                    تایید و ثبت آدرس
                                </v-btn>
                            </div>
                        </div>
                    </div>
                    <div class="col-3"></div>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
// import Swiper from 'swiper';
// import 'swiper/css/swiper.css';
export default {
    layout: 'home',
    mounted(){
        this.$store.commit('_HOME', ['wmenu', 0]);
    },
    data(){
        return{
            /*
            address:{
                name: 'خونه',
                address: 'یزد امام شهر، انتهای بلوار کارگر',
            },
            */
        }
    },
    methods:{
        register(){
            alert('registered!')
        }
    },
    /*
    computed:{
        selectedShop(){
            return this.$store.state._home.selectedShop;
        }
    }*/
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