<template>
    <div class="address-wrapper">


        <div class="fs-14 fw-600 mt-6 mb-2">حساب کاربری من</div>
        <div class="row">
            <div class="col-4">
                <div class="account-menu fs-14">
                    <nuxt-link class="sl" to="/account">
                        <div>
                            <img src="/images/account/user.svg">
                            پروفایل من
                        </div>
                    </nuxt-link>
                    <nuxt-link class="sl" to="/wallet">
                        <div>
                            <img src="/images/account/wallet.svg">
                            کیف پول من
                        </div>
                    </nuxt-link>
                    <nuxt-link class="sl active" to="/address">
                        <div>
                            <img src="/images/account/signs.svg">
                            آدرس های من
                        </div>
                    </nuxt-link>
                    <nuxt-link class="sl" to="/share">
                        <div>
                            <img src="/images/account/share.svg">
                            ثبت و ارسال کد معرف
                        </div>
                    </nuxt-link>
                    <nuxt-link class="sl" to="/gift">
                        <div>
                            <img src="/images/account/gift.svg">
                            کدهای هدیه من
                        </div>
                        <div class="l">
                            <v-badge
                                color="primary"
                                content="2">
                            </v-badge>
                        </div>
                    </nuxt-link>
                    <nuxt-link class="sl" to="/wallet">
                        <div>
                            <img src="/images/account/wallet.svg">
                            لیست خرید من
                        </div>
                    </nuxt-link>
                    <nuxt-link class="sl" to="/support">
                        <div>
                            <img src="/images/account/support.svg">
                            ارتباط با پشتیبانی
                        </div>
                    </nuxt-link>
                </div>
            </div>
            <div class="col-6">
                <div class="row">
                    <div class="col-6 address" v-for="i in 2">
                        <div class="map">
                            <img src="/images/tmp/map.jpg">
                        </div>
                        <div class="mt-2">
                            <div class="sl">
                                <div class="primary--text">خانه</div>
                                <div class="l">
                                    <img src="/images/address/edit_bl.png">
                                    <img src="/images/address/error.svg">
                                </div>
                            </div>
                            <div class="sl">
                                <div class="gray--text fs-12">یزد، امامشهر، انتهای بلوار کارگر، خ شهید حسین کیا، کوچه توحید</div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="row">
                    <div class="col">
                        <div class="checkout  mt-10">
                            <v-btn
                                to="newaddress"
                                color="primary"
                                rounded
                                x-large>
                                افزودن آدرس جدید
                            </v-btn>
                        </div>
                    </div>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
export default {
    layout: 'home',
    mounted(){
        this.$store.commit('_HOME', ['title', 'آدرس های من']);
    },
    data(){
        return{
        }
    },
    methods:{
    }
};
</script>

<style scoped>
.w-50{width: 50%;}
.db{display: block !important;}
.account-menu{
    border: 1px solid #eee;
    border-radius: 10px;
    border-radius: 15px;
    overflow: hidden;
}
.account-menu .sl{
    width: 100%;
    display: inline-block;
    padding: 20px 15px;
    margin-bottom: 0;
    border-bottom: 1px solid #eee;
    color: unset;
}
.account-menu .sl:last-child{
    border-bottom: 0px;
}
.account-menu .sl div{
    display: inline-block;
}
.account-menu .sl .l{
    float: left;
    margin: 5px 14px -5px;
}
.account-menu .sl.btns{
    text-align: center;
    margin-top: 20px;
}
.account-menu .sl.btns > div{
    padding: 0 5px;
    width: 48%;
}
.account-menu .sl.btns button{
    height: 40px;
}
.account-menu img{
    width: 18px;
    vertical-align: middle;
    margin-left: 10px;
}
.account-menu .active{
    background-color: #5e5d5e;
    color: #fff;
}

.address-wrapper{
    padding-bottom: 60px;
}
.address{
    padding: 10px;
    border-radius: 10px;
    box-shadow: 0 0 5px rgba(0,0,0,.15);
    margin-bottom: 20px;
}
.address .map{
    border-radius: 15px;
    overflow: hidden;
    border: 1px solid #cdd0df;
}
.address .sl{
    width: 100%;
    display: inline-block;
}
.address .sl div{
    display: inline-block;
}
.address .sl .l{
    float: left;
}
.address .sl .l img{
    width: 24px;
    margin: 0 10px;
}
.add-address{
    position: fixed;
    bottom: 0;
    width: calc(100% - 20px);
    padding: 20px;
}
</style>