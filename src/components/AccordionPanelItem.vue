<script setup>
import { ref } from "vue";
const props = defineProps(["faq"]);
const isNote = props.faq.note;
const isActive = ref(false);
const toggleClass = () => {
	isActive.value = !isActive.value;
};
</script>

<template>
	<div class="accordion">
		<div class="accordion__title" :data-active="isActive" @click="toggleClass">
			<span class="accordion__icon">Q</span>{{ faq.q }}
		</div>
		<div class="accordion__body" :data-active="isActive">
			<div class="accordion__inner">
				<span class="accordion__icon accordion__icon--a">A</span>
				<p>
					<span>{{ faq.a }}</span>
					<br /><span v-if="isNote" class="accordion__note">{{
						faq.note
					}}</span>
				</p>
			</div>
		</div>
	</div>
</template>

<style scoped>
.accordion {
	width: min(90vw, 750px);
	margin: 0 auto 1rem;
	border: 1px solid var(--vt-c-orange);
	color: var(--color-text);
	cursor: pointer;
}
.accordion__title {
	position: relative;
	padding: 1rem;
	font-weight: 700;
	font-size: 1rem;
	color: var(--vt-c-white);
	cursor: pointer;
	background-color: var(--vt-c-orange);
}
.accordion__title:after,
.accordion__title:before {
	background-color: var(--vt-c-white);
	bottom: 0;
	content: "";
	display: block;
	height: 2px;
	margin: auto 0;
	position: absolute;
	right: 1rem;
	top: 0;
	width: 1rem;
}
.accordion__title:after {
	transform: rotate(270deg);
	transition: transform 0.2s;
}
.accordion__title[data-active="true"]:after {
	transform: rotate(180deg);
}
.accordion__icon {
	font-size: 120%;
	font-weight: bold;
	padding-right: 8px;
}
.accordion__icon--a {
	color: var(--vt-c-orange);
}
.accordion__body {
	padding-inline: 1rem;
	display: grid;
	grid-template-rows: 0fr;
	transition: grid-template-rows 0.2s ease;
	background-color: var(--vt-c-white);
}
.accordion__body[data-active="true"] {
	padding: 1rem;
	grid-template-rows: 1fr;
}
.accordion__inner {
	overflow: hidden;
	display: flex;
}
.accordion__note {
	font-size: 85%;
}
</style>
