<template>
    <div class="account-wrapper">
        <div class="fs-14 fw-600 mt-6 mb-2">حساب کاربری من</div>
        <div class="row">
            <div class="col-4">
                <div class="account-menu fs-14">
                    <nuxt-link class="sl active" to="/account">
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
                        <img class="avatar" src="/images/account/avatar_f.png">
                    </div>
                </div>
                <div class="row">
                    <div class="col"><a-input label="نام شما" required/></div>
                    <div class="col"><a-input label="نام خانوادگی" required/></div>
                </div>
                <div class="row">
                    <div class="col"><a-input label="کد ملی" required/></div>
                    <div class="col"><a-input label="شماره همراه" required/></div>
                </div>
                <div class="row">
                    <div class="col"><a-input label="تاریخ تولد" required/></div>
                    <div class="col"><a-input label="شماره شبا" required/></div>
                </div>
                <div class="row">
                    <div class="col">وضعیت تاهل</div>
                    <div class="col">
                        <label>
                            <input type="radio" name="mariage">
                            متاهل
                        </label>
                        <label>
                            <input type="radio" name="mariage">
                            مجرد
                        </label>
                    </div>
                </div>
                <div class="row">
                    <div class="col">جنسیت</div>
                    <div class="col">
                        <label>
                            <input type="radio" name="gender">
                            زن
                        </label>
                        <label>
                            <input type="radio" name="gender">
                            مرد
                        </label>
                    </div>
                </div>
                <div class="row">
                    <div class="col-8"></div>
                    <div class="col-4">
                        <v-btn @click="register" color="success" elevation="1" block x-large>
                            تایید و ثبت اطلاعات
                        </v-btn>
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
        this.$store.commit('_HOME', ['title', 'منوی کاربری']);
    },
    data(){
        return{
        }
    }
};
</script>

<style scoped>
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

.avatar{
    border: 2px solid #ddd;
    border-radius: 5px;
    max-width: 164px;
    max-height: 164px;
}

</style>