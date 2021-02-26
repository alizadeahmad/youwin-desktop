<template>
	<div class="swiper-slide" :class="{added: isAdded}">
		<div class="product-image">
        	<img :src="image">
		</div>
		<div class="product-name">{{ name }}</div>
		<div class="ac-section text-right pr-2">
			<div class="d-ib mt-5 mr-3">
				<div class="product-price-discount fs-14 gray--text"><span class="price-discount">{{ $cn(priceDiscount) }}</span> <span class="currency">ریال</span></div>
				<div class="product-price primary--text fs-16 mt-2">{{ $cn(price) }} <span class="currency gray--text">ریال</span></div>
			</div>
			<div class="add-cart accent d-ib" @click="isAddedCheck">
				<img src="/images/home/shoppingcart_w.png">
			</div>
		</div>
		<div class="pm-section">
			<div class="minus-cart error--text d-ib" @click="paCountCheck(false)">
				<img src="/images/home/minus.png">
			</div>
			<div class="count-cart d-ib mt-10 fs-16">{{ paCount }}</div>
			<div class="plus-cart secondary--text d-ib" @click="paCountCheck(true)">
				<img src="/images/home/plus.png">
			</div>
		</div>
	</div>
</template>

<script>
export default{
	props:{
		id:{
			type: Number
		},
		image:{
			type: String
		},
		name:{
			type: String
		},
		priceDiscount:{
			type: String
		},
		price:{
			type: String
		}
	},
	data(){
		return{
			paCount: 0,
			isAdded: false,
		}
	},
	methods:{
		isAddedCheck(){
			this.isAdded = true;
			this.paCountCheck(true);
		},
		paCountCheck(s){
			this.paCount = s ? this.paCount+1 : this.paCount-1;
			if(this.paCount == 0){
				this.isAdded = false;
			}
			let obj = {
				id: this.id,
				count: this.paCount,
				name: this.name,
				price: this.price,
				image: this.image
			};
            this.$store.commit('_CART_SYNC', obj);
		},
	},
	watch:{
	}
};
</script>

<style scoped>
.swiper-slide{
	width: 250px;
	height: 360px;
	background-color: #f9f9f9;
	border-radius: 10px;
	box-shadow: 0 4px 6px -3px rgba(0,0,0,.25);
	text-align: center;
}
a{
	text-decoration: none;
}
.product-image{
	padding: 10px;
	max-width: 230px;
	max-height: 230px;
}
.product-image img{
	border-radius: 5px;
	/*width: 100%;*/
}
.product-name{
	/*font-size: 16px;*/
	color: #5d5e5d;
}
.product-price-discount .price-discount{
	text-decoration: line-through;
}
.add-cart{
	padding: 10px;
	width: 36px;
	height: 36px;
	position: absolute;
	bottom: 0;
	left: 0;
	border-radius: 0 10px 0 10px;
	overflow: hidden;
}
.d-ib{
	display: inline-block;
}
.hide{
	display: none;
}

.minus-cart, .plus-cart{
	position: absolute;
	bottom: 0;
	padding: 5px;
	width: 42px;
	height: 42px;
	border: 2px solid;
}
.minus-cart{
	right: 0;
	border-radius: 10px 0 10px 0;
}
.plus-cart{
	left: 0;
	border-radius: 0 10px 0 10px;
}
.pm-section{
	display: none;
}
.swiper-slide.added .ac-section{
	display: none;
}
.swiper-slide.added .pm-section{
	display: block;
}
</style>