<script setup>
import AccordionPanelItem from '@/components/AccordionPanelItem.vue'
const faqs = [
  {
    id: 1,
    q: 'よくある質問1です',
    a: 'よくある回答1ですよくある回答1ですよくある回答1ですよくある回答1ですよくある回答1です',
    note: '※補足が入ります※補足が入ります※補足が入ります※補足が入ります※補足が入ります※補足が入ります',
  },
  {
    id: 2,
    q: 'よくある質問2です',
    a: 'よくある回答2です',
    note: '',
  },
  {
    id: 3,
    q: 'よくある質問3です',
    a: 'よくある回答3ですよくある回答3ですよくある回答3ですよくある回答3ですよくある回答3ですよくある回答3です',
    note: '※補足が入ります',
  },
]
</script>

<template>
  <h1>よくある質問</h1>
  <AccordionPanelItem v-for="faq in faqs" :key="faq.id" :faq="faq" />
</template>

<style scoped></style>
