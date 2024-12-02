<script setup>
import { ref } from 'vue'
const props = defineProps(['faq'])
const isNote = props.faq.note
const isActive = ref(false)
const toggleClass = () => {
  isActive.value = !isActive.value
}
</script>

<template>
  <div class="accordion">
    <div class="accordion-title" :data-active="isActive" @click="toggleClass">
      <span>Q</span>{{ faq.q }}
    </div>
    <div class="accordion-body" :data-active="isActive">
      <div class="accordion-inner">
        <p>
          <span>A</span>{{ faq.a }}<br />
          <span v-if="isNote" class="faq-item__note">{{ faq.note }}</span>
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.accordion {
  margin-bottom: 1rem;
  border: 1px solid limegreen;
  cursor: pointer;
}
.accordion-title {
  position: relative;
  padding: 1rem;
  font-weight: 700;
  font-size: 16px;
  cursor: pointer;
  background-color: limegreen;
}
.accordion-title:after,
.accordion-title:before {
  background-color: #000;
  bottom: 0;
  content: '';
  display: block;
  height: 2px;
  margin: auto 0;
  position: absolute;
  right: 8px;
  top: 0;
  width: 16px;
}
.accordion-title:after {
  transform: rotate(270deg);
  transition: transform 0.2s;
}
.accordion-title[data-active='true']:after {
  transform: rotate(180deg);
}
.accordion-title span:first-child {
  font-size: 120%;
  padding-right: 8px;
}
.accordion-body {
  padding-inline: 1rem;
  display: grid;
  grid-template-rows: 0fr;
  transition: grid-template-rows 0.2s ease;
}
.accordion-body[data-active='true'] {
  grid-template-rows: 1fr;
}
.accordion-inner {
  overflow: hidden;
}
.faq-item__note {
  font-size: 80%;
}
</style>
