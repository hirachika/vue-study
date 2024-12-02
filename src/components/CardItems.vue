<script setup>
// import { ref } from "vue";
const { nameJa, nameEn, price, newPrice, stocks, img } = defineProps({
	nameJa: {
		type: String,
		Required: true,
		default: "",
	},
	nameEn: {
		type: String,
		Required: true,
		default: "",
	},
	price: {
		type: Number,
		Required: true,
		default: 0,
	},
	newPrice: {
		type: Number,
		Required: true,
		default: 0,
	},
	stocks: {
		type: Number,
		Required: true,
		default: 0,
	},
	img: {
		type: String,
		Required: true,
		default: "",
	},
});
</script>

<template>
	<div class="card">
		<figure class="card__img">
			<img :src="img" :alt="name" />
		</figure>
		<p class="card__name">
			{{ nameJa }}<br />{{ nameEn }}<br /><span>残り{{ stocks }}点</span>
		</p>
		<p class="card__price card__price--regular">
			<span class="card__price-yen">&yen;</span>
			<span class="card__price-value card__price-value--regular">{{
				price
			}}</span>
			<span class="card__price-tax">[税込]</span>
		</p>
		<p class="card__price">
			<span class="card__price-yen">&yen;</span>
			<span class="card__price-value card__price-value--new">{{
				newPrice
			}}</span>
			<span class="card__price-tax">[税込]</span>
		</p>
		<a class="card__button" href="">購入する</a>
		<p class="card__note">2点以上購入で送料無料</p>
	</div>
</template>

<style scoped>
.card {
	width: calc(100% / 3 - 0.5rem);
	display: grid;
	grid-template-rows: subgrid;
	grid-row: span 6;
	gap: 8px;
	padding: 16px min(1.4vw, 20px) min(1.4vw, 20px);
	background-color: var(--vt-c-white);
}
.card__img {
	object-fit: cover;
	height: min(16vw, 280px);
	overflow: hidden;
}
.card__img img {
	width: 100%;
	height: auto;
}
.card__name {
	font-weight: 400;
	font-size: 14px;
}
.card__name::first-line {
	font-size: 120%;
}
.card__name span {
	font-weight: 400;
	font-size: 13px;
	letter-spacing: 0.05em;
}
.card__price {
	line-height: 1;
}
.card__price-yen {
	font-size: 80%;
	vertical-align: middle;
}
.card__price-value {
	vertical-align: middle;
}
.card__price-value--regular {
	font-size: 20px;
	text-decoration: line-through;
}
.card__price-value--new {
	font-size: 24px;
	color: var(--vt-c-orange);
}
.card__price-tax {
	font-size: 70%;
	vertical-align: text-bottom;
}
.card__button {
	background-color: var(--vt-c-orange);
	color: #fff;
	font-size: 14px;
	font-weight: bold;
	letter-spacing: 0.08em;
	width: 100%;
	display: flex;
	align-items: center;
	justify-content: center;
	text-decoration: none;
	height: 50px;
	transition: opacity ease-in 0.2s;
}
.card__button:hover {
	opacity: 0.7;
}
.card__note {
	width: 100%;
	font-size: 14px;
	text-align: center;
}
</style>
