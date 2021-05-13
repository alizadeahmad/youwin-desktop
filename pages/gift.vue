<template>
    <div class="gift-wrapper">

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
                    <nuxt-link class="sl active" to="/gift">
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
            <div class="col-8">

                <div class="gift" v-for="i in 2">
                    <div class="gift-c">
                        <span class="r fs-14 text-center">
                            <div>کد تخفیف ویژه عید غدیر خم</div>
                            <div class="b primary--text">GHDR6587</div>
                            <div class="gray--text fs-10">مهلت استفاده تا 99/06/06</div>
                        </span>
                        <span class="l">
                            <span class="copy-gift accent">
                                <img src="/images/gift/copy.svg">
                                کپی
                            </span>
                        </span>
                    </div>
                </div>

                <div class="gift expired">
                    <div class="gift-c">
                        <span class="r fs-14 text-center">
                            <div>کد تخفیف ویژه عید غدیر خم</div>
                            <div class="b gray--text">GHDR6587</div>
                            <div class="error--text fs-10">منقضی شده</div>
                        </span>
                        <span class="l">
                            <span class="copy-gift gray">
                                <img src="/images/gift/copy.svg">
                                کپی
                            </span>
                        </span>
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
        this.$store.commit('_HOME', ['title', 'کدهای هدیه من']);
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

.gift{
    width: 50%;
    display: inline-block;
    padding: 10px;
}
.gift-c{
    padding: 10px;
    border-radius: 10px;
    border: 1px solid #eee;
}
.gift-c > span{
    vertical-align: middle;
}
.gift .r{
    padding: 5px;
    width: calc(65% - 3px);
    display: inline-block;
    border-left: 1px dotted #aaa;
}
.gift .r .b{
    border: 1px solid;
    padding: 10px 30px 5px;
    border-radius: 10px;
    margin: 5px 0;
    display: inline-block;
}
.gift .l{
    text-align: center;
    width: calc(35% - 3px);
    display: inline-block;
}
.copy-gift{
    border-radius: 10px;
    padding: 10px 20px;
    color: #fff;
    font-size: 12px;
    font-weight: 100;
}
.copy-gift img{
    width: 20px;
    vertical-align: middle;
}
</style>