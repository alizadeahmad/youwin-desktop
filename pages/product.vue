<template>
    <div class="">

        <div class="row breadcrumbs">
            <div class="col-9">
                <v-breadcrumbs :items="items"></v-breadcrumbs>
            </div>
        </div>
  
        <div class="row">
            <div class="col products-box">
                <div class="row">
                	<div class="col-4">
                		<div class="row p-relative">
                			<div class="discunt">
                				<div>-10</div>
                				<div>%</div>
                			</div>
                			<div class="col-12"><img class="img-main" src="images/tmp/3.png"></div>
                			<div class="col-12">
                				<img class="img-thumb" src="images/tmp/3.png">
                				<img class="img-thumb" src="images/tmp/3.png">
                				<img class="img-thumb" src="images/tmp/3.png">
                			</div>
                		</div>
                	</div>
                	<div class="col-8">
                		<div class="prod-head">
	                		<div class="fs-22 fw-500">شیر پر چرب هراز حجم 1 لیتر</div>
	                		<div class="mt-4">
	                			<Stars rate="3" class="prod-star"/>
	                			<span class="mr-3 gray--text fs-14">امتیاز: 3</span>
	                		</div>
                		</div>
                		<div class="prod-desc">
                			<div class="fs-18 gray--text">توضیحات</div>
                			<div class="w-50 fs-18 gray--text">شیر پر چرب هراز حجم 1 لیتر شیر پر چرب هراز حجم 1 لیتر شیر پر چرب هراز حجم 1 لیتر شیر پر چرب هراز حجم 1 لیتر شیر پر چرب هراز حجم 1 لیتر </div>
                		</div>
                		<div class="prod-acart w-50">
                			<div class="">
                				<div class="gray--text fw-400 td-lt">120,000 ریال</div>
                				<div class="fs-22 fw-500 mt-4 success--text">110,000 <span class="gray--text"> ریال</span></div>
                			</div>
                			<div class=""></div>
                			<div class=""></div>
                		</div>
                	</div>
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
            items: [
                {text: 'دسته بندی ها', disabled: false, href: '/'},
                {text: 'شیر و فراورده های لبنی', disabled: false, href: 'categories'},
                {text: 'شیر پر چرب هراز 1 لیتری', disabled: true, href: '/'},
            ],
        }
    },
    methods:{
        register(){
            alert('registered!')
        }
    },
};
</script>

<style>
.td-lt{text-decoration: line-through;}
.w-50{width: 50%;}
.vam{vertical-align: middle;}
.p-relative{position: relative;}
.discunt{
	direction: ltr;
	position: absolute;
    background-color: #f00;
    width: 50px;
    height: 80px;
    font-size: 22px;
    color: #fff;
    font-weight: 500;
    text-align: center;
    padding: 10px 0;
    border-radius: 6px;
    left: 10px;
    top: 10px;
}
.img-main{
	box-shadow: 0 0 2px rgba(0,0,0,.5);
	padding: 10px;
	border-radius: 5px;
}
.img-thumb{
	max-width: 64px;
	max-height: 64px;
	padding: 10px;
	box-shadow: 0 0 2px rgba(0,0,0,1);
	margin-left: 5px;
	border-radius: 5px;
}
.prod-head{
	border-bottom: 1px solid #eee;
	padding-bottom: 25px;
}
.prod-desc{
	border-bottom: 1px solid #eee;
	padding: 25px 0;
}
.prod-acart{
	padding-top: 25px;
}

.slider-default{
    overflow: hidden;
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
<style>
.prod-star{
	display: inline-block;
}
.prod-star .star{
	width: 20px;
	height: 20px;
}
</style>