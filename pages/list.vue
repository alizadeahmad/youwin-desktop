<template>
    <div class="list-wrapper">
 
        <transition name="fade">
            <div class="modal" v-if="showListModal" @click="closeShowListModal">
                <div class="modal-wrapper pb-4" @click.stop>
                    <div class="modal-header text-center gray--text mt--15 mb-2 fs-14">
                        لیست خرید خانه
                    </div>
                    <div class="modal-body">
                        <div class="products-item fs-14 fw-500">
                            <div class="sl" v-for="i in 5" :key="i">
                                <div class="product-name">
                                    <img src="/images/tmp/1.jpg">
                                    شیر پر چرب هراز حجم 1 لیتر
                                </div>
                                <div class="l"><img src="/images/list/3.png"></div>
                            </div>
                            <div class="sl">
                                <div class="product-name">
                                    <img src="/images/tmp/2.jpg">
                                    آبمیوه سیب موز سان استار
                                </div>
                                <div class="l"><img src="/images/list/3.png"></div>
                            </div>
                        </div>
                    </div>
                    <div class="modal-footer"></div>
                </div>
            </div>
        </transition>

        <transition name="fade">
            <div class="modal" v-if="addListModal" @click="closeAddListModal">
                <div class="modal-wrapper pb-4" @click.stop style="max-width:400px;">
                    <div class="modal-header"></div>
                    <div class="modal-body">
                        <a-input
                            v-model="vModel"
                            label="انتخاب نام لیست"
                            placeholder="مثلا: خرید منزل، خرید مهمانی و..."
                            required />
                        <v-btn
                            to="/listSelect"
                            class="mt-10"
                            color="secondary"
                            elevation="1"
                            rounded
                            block
                            x-large>
                            تایید و انتخاب اقلام
                        </v-btn>
                    </div>
                    <div class="modal-footer"></div>
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
                    <nuxt-link class="sl active" to="/list">
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

                <div class="list-empty" v-if="!list">
                    <div>
                        <img src="/images/list/list.svg">
                        <div class="mt-4 fs-14 gray--text">لیست های خرید شما در این قسمت ثبت می شوند</div>
                    </div>
                </div>

                <div class="add-list gray--text text-center">
                    <div class="mt-4">
                        <v-btn
                            @click="openAddListModal"
                            color="secondary"
                            elevation="1"
                            rounded
                            x-large>
                            افزودن لیست خرید جدید
                        </v-btn>
                    </div>
                </div>

                <div class="lists" v-if="list">
                    <div class="list">
                        <span class="gray--text">لیست خرید خانه</span>
                        <span class="list-action">
                            <img src="/images/list/1.png">
                            <img src="/images/list/2.png" @click="openShowList">
                            <img src="/images/list/3.png">
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
    mounted() {
        this.$store.commit('_HOME', ['wmenu', 4]);
    },
    data(){
        return{
            vModel: '', // temp
            list: false,
            addListModal: false,
            showListModal: false,
        }
    },
    methods:{
        openAddListModal(){
            this.addListModal = true;
            this.list = true;
        },
        closeAddListModal(){
            this.addListModal = false;
        },
        openShowList(){
            this.showListModal = true;
        },
        closeShowListModal(){
            this.showListModal = false;
        },
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

.list-wrapper{
    padding-bottom: 160px;
}
.list-empty{
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    /*margin-top: calc(50vh - 142px);*/
}
.list-empty img{
    width: 96px;
}
.add-list{
    /*position: fixed;*/
    /*bottom: 60px;*/
    /*width: calc(100% - 20px);*/
    padding: 20px;
}

.list{
    border: 1px solid #ddd;
    border-radius: 10px;
    padding: 20px;
    font-size: 14px;
}
.list-action{
    float: left;
    margin-top: -7px;
}
.list-action img{
    width: 36px;
    border-radius: 50%;
    /*vertical-align: middle;*/
}

.products-item{
    padding: 0;
}
.products-item .sl{
    padding: 10px;
    margin-bottom: 0;
    border-bottom: 1px solid #eee;
}
.products-item .sl:last-child{
    border-bottom: 0px;
}
.products-item .sl div{
    display: inline-block;
}
.product-name img{
    width: 48px;
    vertical-align: middle;
    margin-left: 10px;
}
.products-item .l{
    padding-top: 5px;
    float: left;
}
.products-item .l img{
    width: 36px;
    height: 36px;
    border-radius: 30%;
}
</style>