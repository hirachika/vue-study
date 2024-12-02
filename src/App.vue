<script setup>
import AccordionPanelItems from "@/components/AccordionPanelItems.vue";
import CardItems from "@/components/CardItems.vue";
const items = [
	{
		id: 1,
		nameJa: "カラフルスニーカー",
		nameEn: "SNEAKER",
		price: 5500,
		newPrice: 4800,
		stocks: 5,
		img: "https://picsum.photos/id/237/200/300",
	},
	{
		id: 2,
		nameJa: "メンズスニーカー",
		nameEn: "MENS SNEAKER",
		price: 3980,
		newPrice: 2980,
		stocks: 7,
		img: "https://picsum.photos/id/237/200/300",
	},
	{
		id: 3,
		nameJa: "ビジネスジューズ",
		nameEn: "BLACK SNEAKER",
		price: 4200,
		newPrice: 3980,
		stocks: 3,
		img: "https://picsum.photos/200/300?grayscale",
	},
];
const faqs = [
	{
		id: 1,
		question: "ログインができません",
		answer:
			"いくつかの原因が考えられます。ログインができないお客様は、以下の解決ヒントをご確認いただき、再度ログインをお試しください。",
		note: "",
	},
	{
		id: 2,
		question: "レッスン予約は何分前までできますか？",
		answer: "レッスン開始時間の15分前まで可能です。",
		note: "",
	},
	{
		id: 3,
		question: "どのような支払い方法がありますか？",
		answer:
			"「クレジットカード支払い」「DMMポイント支払い」の2種類となります。",
		note: "※1つの決済で複数のお支払い方法を選ぶことはできません。",
	},
];
</script>

<template>
	<h1>パーツ</h1>
	<section>
		<h2>ご購入はこちら</h2>
		<div class="cards">
			<CardItems
				v-for="item in items"
				:key="item.id"
				:name-ja="item.nameJa"
				:name-en="item.nameEn"
				:price="item.price"
				:new-price="item.newPrice"
				:stocks="item.stocks"
				:img="item.img"
			/>
		</div>
	</section>
	<section>
		<h2>よくある質問</h2>
		<AccordionPanelItems
			v-for="faq in faqs"
			:key="faq.id"
			:question="faq.question"
			:answer="faq.answer"
			:note="faq.note"
		/>
	</section>
</template>

<style scoped>
h1,
h2 {
	margin: 1rem auto;
	text-align: center;
}
section:nth-of-type(even) {
	background-color: var();
}
.cards {
	display: flex;
	justify-content: space-between;
}
</style>
