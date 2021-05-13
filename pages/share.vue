<template>
    <div class="share-wrapper mt-6">
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
                    <nuxt-link class="sl active" to="/share">
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
            <div class="col-8">
                <div class="row">
                    <div class="col-6 insert-code">
                        <p class="gray--text fs-14">در صورتی که دوستان شما یووین را به شما معرفی کرده اند با ثبت کد معرف دوستان خود از هدیه یووین بهره مند شوید</p>
                        <div class="ic mt-6">
                            <div class="r">
                                <a-input
                                    v-model="vModel"
                                    label="کد تخفیف"
                                    required /> 
                            </div>
                            <div class="l">
                                <v-btn
                                    class="cbtn"
                                    x-large
                                    color="secondary">
                                    <v-icon dark>
                                        done
                                    </v-icon>
                                </v-btn>
                            </div>
                        </div>
                    </div>
                    <div class="col-6 share fs-14 text-center">
                        <p class="gray--text">با ارسال کد اختصاصی زیر، دوستانت رو به یووین دعوت کن. یووین با هر خرید دوستانت کیف پولت رو شارژ می کنه</p>
                        <p class="black--text fw-500 mt-5">کد اختصاصی شما</p>
                        <p class="black--text fw-500 mt--10 mb-5">ABCDEFGHI</p>
                        <p class="gray--text">لینک دعوت خود را به اشتراک بگذارید</p>
                        <div class="socials mt-6">
                            <div class="social" v-for="i in socials">
                                <img :src="i.img" @click="sharing(i.action)">
                            </div>
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
        this.$store.commit('_HOME', ['title', 'ثبت و ارسال کد معرف']);
    },
    data(){
        return{
            vModel: '', // temp
            socials:[
                // {img:'/images/share/socials/blogger.svg', action:'a'},
                // {img:'/images/share/socials/busuu.svg', action:'b'},
                // {img:'/images/share/socials/dropbox.svg', action:'c'},
                // {img:'/images/share/socials/facebook.svg', action:'d'},
                // {img:'/images/share/socials/foursquare.svg', action:'e'},
                // {img:'/images/share/socials/google-allo.svg', action:'f'},
                // {img:'/images/share/socials/google-drive.svg', action:'g'},
                {img:'/images/share/socials/instagram.svg', action:'h'},
                // {img:'/images/share/socials/line.svg', action:'i'},
                // {img:'/images/share/socials/linkedin.svg', action:'j'},
                // {img:'/images/share/socials/skype.svg', action:'k'},
                {img:'/images/share/socials/telegram.svg', action:'l'},
                {img:'/images/share/socials/twitter.svg', action:'m'},
                // {img:'/images/share/socials/viber.svg', action:'n'},
                // {img:'/images/share/socials/wechat.svg', action:'o'},
                {img:'/images/share/socials/whatsapp.svg', action:'p'},
            ]
        }
    },
    methods:{
        sharing(e){
            if(e == 'a') alert('Share to Blogger!');
            else if(e == 'b') alert('Share to Busuu!');
            //else if(e == ...) alert('Share to ...!');
            else alert('Share to another!');
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

.insert-code{
    /*margin: 0px -10px 0;*/
    /*padding: 10px 10px 0;*/
    border-left: 1px solid #ddd;
}
.insert-code .ic > div{
    display: inline-block;
}
.insert-code .ic .r{
    width: calc(100% - 60px);
}
.insert-code .ic .l{
    width: 55px;
    text-align: left;
}
.cbtn{
    min-width: 49px !important;
    max-width: 49px !important;
    border-radius: 8px;
    height: 49px !important;
}

.social{
    display: inline-block;
    width: 68px;
    height: 64px;
}
.social img{
    width: 32px;
}

</style>