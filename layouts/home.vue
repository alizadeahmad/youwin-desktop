<template>
  <v-app>


    <transition name="fade">
        <div class="modal modal-desktop" v-if="loginModal" @click="closeLoginModal">
            <div class="modal-wrapper pb-4" @click.stop>
                <div class="modal-header text-center fs-14 gray--text mb-4">
                    برای ورود به وبسایت شماره همراه خود را وارد کنید
                </div>
                <div class="modal-body">

                    <div class="row">
                        <div class="col-12">
                            <a-input
                                label="شماره همراه"
                                icon="phone_android"
                                required />
                        </div>
                        <div class="col-12">
                            <v-btn
                                @click="getPhone"
                                color="accent"
                                elevation="1"
                                rounded
                                block
                                x-large>
                                دریافت کد
                            </v-btn>
                        </div>
                    </div>

                </div>
                <div class="modal-footer"></div>
            </div>
        </div>
    </transition>


    <transition name="fade">
        <div class="modal modal-desktop" v-if="!modalSelectShop" @click="closeModalSelectShop">
            <div class="modal-wrapper pb-4" @click.stop>
                <div class="modal-header text-center fs-14 gray--text mb-4"></div>
                <div class="modal-body">

                	<div class="row">
                		<div class="col">
    					        <div class="a-select-wrapper mb-6">
    					            <label>انتخاب استان</label>
    					            <select>
    					                <option>-</option>
    					                <option>تهران</option>
    					                <option>یزد</option>
    					            </select>
    					            <i class="material-icons">keyboard_arrow_down</i>
    					        </div>
                		</div>
                		<div class="col">
    					        <div class="a-select-wrapper mb-6">
    					            <label>انتخاب شهر</label>
    					            <select>
    					                <option>-</option>
    					            </select>
    					            <i class="material-icons">keyboard_arrow_down</i>
    					        </div>
                		</div>
                	</div>

                    <div class="shops" @click="selectedShop(i)" v-for="i in 2">
                        <div class="shop-logo">
                            <img class="logo" src="/images/home/ok.png">
                            <Stars rate="3" class="shop-star"/>
                        </div>
                        <div class="shop-name pt-1 pr-3">
                            <h1 class="primary--text fs-14">فروشگاه افق کوروش {{ i }}</h1>
                            <div class="gray--text mt-3 fs-11">یزد، بلوار 22 بهمن، جنب چرخ گردون</div>
                        </div>
                    </div>
                </div>
                <div class="modal-footer"></div>
            </div>
        </div>
    </transition>

  	<div class="header">
		<div class="header-sec text-right" style="max-width:200px;">
			<img src="/images/home/logo.png" style="height:42px;margin:19px;">
		</div>
		<div class="header-sec">
            <div class="search mt-5">
                <a-input placeholder="جستجو..." />
	            <v-btn
	            	class="search-btn"
	                color="primary"
	                elevation="1"
	                to="/search">
	                <i class="material-icons">search</i>
	            </v-btn>
            </div>
		</div>
		<div class="header-sec text-left mx-5 mt-3">
			<div class="account fs-14">
				<div class="ml-6">
					<img src="/images/account/avatar_f.png" style="vertical-align:middle;border-radius:50%;width:42px;margin:9px 5px;">
					<nuxt-link class="accent--text" to="/login">ورود / ثبت نام</nuxt-link>
				</div>
				<div>
		            <v-btn
		            	class="cart-i"
		                color="primary"
		                elevation="1"
		                to="/cart">
							<img src="/images/home/shoppingcart_w.png" style="width:32px;border-left:1px solid rgba(255,255,255,.5);padding-left:10px">
			                <span class="mx-5"><span class="cart-price">{{ cart_price }}</span> تومان</span>
		            </v-btn>
				</div>
			</div>
		</div>
  	</div>
  	<div class="body">
  		<div class="nav">
  			<div class="shop-info">
  				<img class="shop-img" src="/images/home/ds.png">
  				<span class="fs-15 fw-500 mr-2 gray--text">انتخاب کنید</span>
  				<span class="shop-chevron"><i class="material-icons">expand_more</i></span>
  			</div>
  			<div class="menus">
  				<ul>
  					<li class="active"><nuxt-link to="/">صفحه اصلی</nuxt-link></li>
  					<li><nuxt-link to="/">درباره ما</nuxt-link></li>
  					<li><nuxt-link to="/">تماس با ما</nuxt-link></li>
  					<li><nuxt-link to="/">مجله خبری</nuxt-link></li>
  				</ul>
  			</div>

	        <div class="current-address accent--text fs-13 fw-500">
	            آدرس من:
	            <span>
	                <span class="mr-1 primary--text">{{ address.name }}</span>
	                <span class="gray--text fw-300">{{ address.address }}</span>
	            </span>
	            <span class="float-left" @click="changeAddress">
	                <i class="material-icons success--text fs-18">sync_alt</i>
	            </span>
	        </div>

  		</div>
  		<Nuxt />
  	</div>
  	<div class="footer">
  		<div class="foot-top df">
  			<div class="f1">
  				<img src="/images/footer/1.png">
  				<span>تضمین اصالت کالا</span>
  			</div>
  			<div class="f1">
  				<img src="/images/footer/2.png">
  				<span>پرداخت اینترنتی</span>
  			</div>
  			<div class="f1">
  				<img src="/images/footer/3.png">
  				<span>ارسال سریع سفارشات</span>
  			</div>
  			<div class="f1">
  				<img src="/images/footer/4.png">
  				<span>پشتیبانی 24 ساعته</span>
  			</div>
  		</div>
  		<div class="foot-mid df fw-300">
  			<div class="f1">
  				<div class="text-center"><img src="/images/home/logo.png" width="168"></div>
  				<div class="fs-13">سیت بای یک سامانه سفارش و خرید اینترنتی اقلام ضروری است که به شما این امکان را می دهد تا محصولات مورد نظر خود را به صورت آنلاین از نزدیک ترین فروشگاه سفارش دهید و بدون صرف وقت و انرژی جهت مراجعه به فروشگاه سفارش خود را درب منزل تحویل بگیرید</div>
  				<div class="mt-4 fm-info"><img src="/images/signs.svg">آدرس: یزد، امامشهر، انتهای بلوار کارگر</div>
  				<div class="mt-4 cn fm-info"><img src="/images/phone-call.svg">{{ $cn('لفن: 03535229262 - 09134545624', 0) }}</div>
  				<div></div>
  			</div>
  			<div class="f1 fm-soc pt-7 text-center">
  				<div>شبکه های اجتماعی</div>
  				<div class="mt-10">
  					<ul>
  						<li><a href="#"><img src="/images/share/socials/instagram.svg">اینستاگرام</a></li>
  						<li><a href="#"><img src="/images/share/socials/twitter.svg">توییتر</a></li>
  						<li><a href="#"><img src="/images/share/socials/telegram.svg">تلگرام</a></li>
  						<li><a href="#"><img src="/images/share/socials/whatsapp.svg">واتساپ</a></li>
  					</ul>
  				</div>
  			</div>
  			<div class="f1 fm-lnk pt-7 text-center">
  				<div>لینک های مفید</div>
  				<div class="mt-10">
  					<ul>
  						<li><a href="#">تماس با ما</a></li>
  						<li><a href="#">درباره ما</a></li>
  						<li><a href="#">راهنمای خرید</a></li>
  						<li><a href="#">قوانین و مقررات</a></li>
  						<li><a href="#">سوالات متداول</a></li>
  						<li><a href="#">حفظ حریم خصوص</a></li>
  					</ul>
  				</div>
  			</div>
  			<div class="f1 fm-cer pt-7 text-center">
  				<div>مجوز های ما</div>
  				<div class="mt-10"><img src="/images/enamad.png"></div>
  			</div>
  		</div>
  		<div class="foot-bot">
  			کلیه حقوق محفوظ است
  		</div>
  	</div>
  </v-app>
</template>

<script>
export default{
	data(){
		return{
            loginModal: false,
			search: '',
			cart_price: 123,
            modalAddress: false,
            address:{
                name: '',
                address: 'موقعیت فعلی',
            },
		}
	},
	methods:{
        changeAddress(){
            this.modalAddress = true;
        },
        openLoginModal(){
            this.loginModal = true;
        },
        closeLoginModal(){
            this.loginModal = false;
        },

		menuSit(i){
            this.$store.commit('_HOME', ['wmenu', i]);
		},
		changeShop(){
            this.$store.commit('_HOME', ['selectedShop', null]);
		},
        closeModalSelectShop(){

        },
        selectedShop(i){
            this.$store.commit('_HOME', ['selectedShop', i]);
        },
        /*
        goAcoount(){
        	this.$router.push('/account');
        },
        goNotif(){
        	this.$router.push('/notif');
        }
        */
	},
	computed:{
		wmenu(){
            return this.$store.state._home.wmenu;
		},
        _CART() {
            let _cart = this.$store.state._CART;
            return _cart;
        },
        modalSelectShop(){
            return this.$store.state._home.selectedShop;
        }
    },

};
</script>

<style>
.df{
	display: flex;
}
.f1{
	flex: 1;
}
.header{
	position: fixed;
	top: 0;
	left: 0;
	background-color: #fff;
	width: 100%;
	height: 80px;
	box-shadow: 0 0 1px rgba(35,40,45,.25);
	display: flex;
	z-index: 98;
}
.header-sec{
	flex: 1;
}
.header-sec .search .a-input-wrapper{
	width: calc(100% - 120px);
	display: inline-block;
}
.header-sec .search input{
	padding: 6px !important;
}
.header-sec .account > div{
	display: inline-block;
}
.header-sec .account a{
	text-decoration: none;
}
.body{
	margin: 80px 0 10px;
	padding: 10px;
}
.nav{
	display: flex;
	margin: 10px 0 20px;
  padding-bottom: 10px;
  border-bottom: 1px solid #eee;
}
.shop-img{
	width: 36px;
	border-radius: 50%;
	vertical-align: middle;
}
.shop-chevron{
	vertical-align: bottom;
}
.menus{
  margin-right: 50px;
}
.menus li.active{
  border-bottom: 3px solid #fc5830;
}
.menus li.active a{
  color: #000;
}
.menus li{
	padding: 10px;
	margin: 0 5px;
	font-size: 15px; 
	display: inline-block;
}
.menus li a{
	color: #373e48;
	text-decoration: none;
}
.current-address{
	flex: 1;
	text-align: left;
	padding-top: 12px;
}
.footer{
}
.foot-top{
	padding: 20px 0;
	background-color: rgb(151,151,148);
	color: #fff;
	font-size: 14px;
}
.foot-top > div{
	text-align: center;
}
.foot-top img{
	vertical-align: middle;
}
.foot-mid{
	padding: 20px;
	background-color: rgb(93,93,92);
	color: #fff;
	font-size: 14px;
}
.foot-mid .fm-info img{
	width: 18px;
	vertical-align: middle;
	margin-left: 10px;
}
.foot-mid .fm-soc ul{
	list-style: none;
}
.foot-mid .fm-soc li{
	margin: 15px 5px;
}
.foot-mid .fm-soc li a{
	color: #fff;
	text-decoration: none;
}
.foot-mid .fm-soc img{
	width: 32px;
	vertical-align: middle;
	margin-left: 10px;
}
.foot-mid .fm-lnk ul{
	list-style: none;
}
.foot-mid .fm-lnk li{
	margin: 10px 5px;
}
.foot-mid .fm-lnk li a{
	color: #fff;
	text-decoration: none;
}
.foot-mid .fm-cer img{
	border-radius: 15px;
}
.foot-bot{
	text-align: center;
	padding: 15px 0;
	background-color: rgb(74,74,73);
	color: #fff;
	font-size: 12px;
}


.shops{
    display: flex;
    border: 1px solid lightgray;
    border-radius: 10px;
    padding: 10px 10px 0;
    margin-bottom: 10px;
}
.shops .shop-logo .logo{
    max-width: 64px;
    max-height: 64px;
    border-radius: 10px;
}
.shops .shop-star{
    margin-top: -8px;
}
</style>