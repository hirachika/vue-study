<script setup>
import AccordionPanelItem from "@/components/AccordionPanelItem.vue";
const faqs = [
	{
		id: 1,
		q: "ログインができません",
		a: "いくつかの原因が考えられます。ログインができないお客様は、以下の解決ヒントをご確認いただき、再度ログインをお試しください。",
		note: "",
	},
	{
		id: 2,
		q: "レッスン予約は何分前までできますか？",
		a: "レッスン開始時間の15分前まで可能です。",
		note: "",
	},
	{
		id: 3,
		q: "どのような支払い方法がありますか？",
		a: "「クレジットカード支払い」「DMMポイント支払い」の2種類となります。",
		note: "※1つの決済で複数のお支払い方法を選ぶことはできません。",
	},
];
</script>

<template>
	<h1>よくある質問</h1>
	<AccordionPanelItem v-for="faq in faqs" :key="faq.id" :faq="faq" />
</template>

<style scoped>
h1 {
	margin: 1rem auto;
	text-align: center;
}
</style>
