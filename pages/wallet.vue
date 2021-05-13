<template>
    <div class="wallet-wrapper">

        <transition name="fade">
            <div class="modal" v-if="modal" @click="closeModal">
                <div class="modal-wrapper pb-4 w-50" @click.stop>
                    <div class="modal-header text-center mt--10 mb-6 fs-18 fw-500">
                        مبلغ قابل تسویه: {{ $cn(250000) }} ریال
                    </div>
                    <div class="modal-body">
                        <div class="shaba-info fs-12 gray--text">
                            <div>
                                <span>شماره شبا</span>
                                <span class="float-left">IR0200 0000 0000 5680211456</span>
                            </div>
                            <div class="mt-4">
                                <span>به نام</span>
                                <span class="float-left">حسین شمس</span>
                            </div>
                        </div>
                    </div>
                    <div class="modal-footer">
                        <div class="mt-6">
                            <span class="btns-wrapper r">
                                <v-btn
                                    color="secondary"
                                    block
                                    rounded
                                    x-large>
                                    تایید و تسویه حساب
                                </v-btn>
                            </span>
                            <span class="btns-wrapper l">
                                <v-btn
                                    @click="closeModal"
                                    color="error"
                                    text
                                    x-large>
                                    انصراف
                                </v-btn>
                            </span>
                        </div>
                    </div>
                </div>
            </div>
        </transition>



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
                    <nuxt-link class="sl active" to="/wallet">
                        <div>
                            <img src="/images/account/wallet.svg">
                            کیف پول من
                        </div>
                    </nuxt-link>
                    <nuxt-link class="sl" to="/address">
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
                    <nuxt-link class="sl" to="/list">
                        <div>
                            <img src="/images/account/list.svg">
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
                    <div class="col text-center">
                        <span class="fs-16">موجودی فعلی:</span>
                        <span class="mr-4 mt-2 fs-24 success--text">{{ $cn(250000) }} <span class="fs-12">ریال</span></span>
                    </div>
                </div>

                <div class="row fs-14 fw-600 mt-10 mb-2">
                    <div class="col-2"></div>
                    <div class="col">افزایش اعتبار</div>
                </div>
                <div class="row mb-10">
                    <div class="col-2"></div>
                    <div class="col-8 increase-credit fs-14 p-5">
                        <div class="text-center">
                            <div class="ic">{{ $cn(100000) }} ریال</div>
                            <div class="ic">{{ $cn(200000) }} ریال</div>
                            <div class="ic">{{ $cn(500000) }} ریال</div>
                        </div>
                        <div class="text-center mt-10">
                            <img src="/images/home/minus.png" class="icb error--text">
                            <span class="ict gray--text">مبالغ دیگر</span>
                            <img src="/images/home/plus.png" class="icb secondary--text">
                        </div>
                        <div class="text-center mt-10">
                            <v-btn
                                color="primary"
                                block1
                                rounded
                                x-large>
                                افزایش اعتبار
                            </v-btn>
                        </div>
                    </div>
                    <div class="col-2"></div>
                </div>

                <div class="row fs-14 fw-600 mt-10 mb-2">
                    <div class="col-2"></div>
                    <div class="col">سوابق پورسانت من</div>
                </div>
                <div class="row mb-10">
                    <div class="col-2"></div>
                    <div class="col-8 fs-14 commission-s">
                        <div class="commission-summary">
                            <div class="commission fs-14">
                                <div class="sl">
                                    <div class="gray--text fs-12">موجودی کیف پول:</div><div class="l">{{ $cn(2250000) }} ریال</div>
                                </div>
                                <div class="sl">
                                    <div class="gray--text fs-12">درآمد 30 روز گذشته از خرید دوستان:</div><div class="l">{{ $cn(2250000) }} ریال</div>
                                </div>
                                <div class="sl">
                                    <div class="gray--text fs-12">درآمد 30 روز گذشته از خرید من:</div><div class="l">{{ $cn(2250000) }} ریال</div>
                                </div>
                                <div class="sl">
                                    <div class="gray--text fs-12">درآمد کل از سامانه:</div><div class="l">{{ $cn(2250000) }} ریال</div>
                                </div>
                            </div>
                        </div>
                        <div class="commission mt-6 fs-14 err">
                            <div class="sl">
                                <div class="b">برداشت از کیف پول</div><div class="l">مبلغ: {{ $cn(250000) }} ریال</div>
                                <div class="d">بابت تسویه حساب کیف پول</div>
                            </div>
                        </div>
                        <div class="commission mt-6 fs-14 war">
                            <div class="sl">
                                <div class="b">برداشت از کیف پول</div><div class="l">مبلغ: {{ $cn(250000) }} ریال</div>
                                <div class="d">بابت تسویه حساب کیف پول</div>
                            </div>
                        </div>
                        <div class="commission mt-6 fs-14 suc">
                            <div class="sl">
                                <div class="b">برداشت از کیف پول</div><div class="l">مبلغ: {{ $cn(250000) }} ریال</div>
                                <div class="d">بابت تسویه حساب کیف پول</div>
                            </div>
                        </div>
                        <div class="checkout text-center mt-10">
                            <v-btn
                                @click="openModal"
                                color="primary"
                                rounded
                                x-large>
                                تسویه حساب
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
        this.$store.commit('_HOME', ['title', 'کیف پول من']);
    },
    methods:{
        openModal(){
            this.modal = true;
        },
        closeModal(){
            this.modal = false;
        }
    },
    data(){
        return{
            modal: false
        }
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

.wallet-wrapper{
    padding-bottom: 60px;
}
.wallet-summary{
    margin: 16px -10px 0;
    padding-bottom: 20px;
    border-bottom: 1px solid #eee;
}
.wallet-summary .sl > div{
    display: inline-block;
    width: calc(50% - 3px);
    text-align: center;
}
.wallet-summary img{
    width: 36px;
}
.wallet-summary .hw{
    display: inline-block;
    width: 100px;
    height: 100px;
    padding: 20px 0;
    color: #33cf86;
    background-color: #effff8;
    border: 1px solid;
    border-radius: 10px;
    text-decoration: none;
}
.increase-credit{
    border: 1px solid #eee;
    padding: 40px 10px;
    border-radius: 10px;
    box-shadow: 0 4px 12px rgba(0,0,0,.15);
}
.increase-credit .ic{
    border: 1px solid #8cc152;
    display: inline-block;
    padding: 10px 20px;
    font-size: 16px;
    margin: 0 5px;
    border-radius: 10px;
}
.increase-credit .icb{
    width: 32px;
    border: 2px solid;
    border-radius: 50%;
    vertical-align: middle;
}
.increase-credit .ict{
    margin: 0 50px;
}
/*---------------*/
.commission-s{
    border: 1px solid #eee;
    padding: 40px 10px;
    border-radius: 10px;
    box-shadow: 0 4px 12px rgba(0,0,0,.15);
}
.commission{
    padding: 20px 20px 10px;
    border-radius: 10px;
}
.commission-summary{
    padding: 10px 10px 20px;
    margin: 0 -10px;
    border-bottom: 1px solid #eee;
}
.commission-summary .commission{
    border: 1px dashed;
    color: #33cf86;
    background-color: #effff8;
    box-shadow: 0 0 0 transparent;
}
.commission .sl{
    margin-bottom: 10px;
    width: 100%;
    display: inline-block;
}
.commission .sl div{
    display: inline-block;
}
.commission .sl .l{
    float: left;
}

.commission{
    border-radius: 10px;
    box-shadow: 0 3px 5px rgba(0,0,0,.15);
}
.commission .b{
    font-weight: 600;
}
.commission .d{
    margin-top: 10px;
    font-size: 12px;
    display: block !important;
}
.commission.err{
    background-color: #ffe9ee;
}
.commission.err .b{
    color: #f1224c;
}
.commission.war{
    background-color: #ffecd6;
}
.commission.war .b{
    color: #ff8900;
}
.commission.suc{
    background-color: #effff8;
}
.commission.suc .b{
    color: #5cd99f;
}

.shaba-info{
    background-color: #f2f2f2;
    padding: 10px;
    border-radius: 10px;
}
.btns-wrapper{
    display: inline-block;
    text-align: center;
}
.btns-wrapper.r{
    width: calc(70% - 3px);
}
.btns-wrapper.l{
    width: calc(30% - 3px);
}
</style>