<template>
  <div class="max-w-2xl mx-auto p-6">
    <h2 class="text-3xl font-bold text-center mb-2">I CAN HELP YOU WITH</h2>
    <p class="text-center text-gray-500 mb-6 text-lg">Most frequent questions and answers</p>
    
    <div v-for="(item, index) in items" :key="index" class="mb-6">
      <div @click="toggle(index)" class="cursor-pointer p-6 bg-white rounded-lg shadow flex justify-between items-center text-xl transition-all duration-700 ease-in-out">
        <span class="font-semibold">{{ item.title }}</span>
        <span :class="{'rotate-180 text-blue-500': activeIndex === index}" class="transition-transform duration-500 ease-out text-2xl">▼</span>
      </div>
      <div 
        class="overflow-hidden transition-[max-height] duration-700 ease-in-out bg-gray-100 rounded-b-lg text-gray-600 text-lg leading-relaxed" 
        :style="{ maxHeight: activeIndex === index ? '500px' : '0px', opacity: activeIndex === index ? '1' : '0', padding: activeIndex === index ? '24px' : '0px', transition: 'max-height 0.7s ease-in-out, opacity 0.5s ease-in-out, padding 0.5s ease-in-out' }">
        {{ item.content }}
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const activeIndex = ref(null);
const items = ref([
  { title: '1:1 Coaching', content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae.' },
  { title: 'Personal Development', content: 'Improve yourself with our guidance. We provide structured plans and expert advice to help you achieve personal growth and success in various aspects of life.' },
  { title: 'Self Oriented Life Programs', content: 'Discover self-improvement strategies. Our programs are tailored to help you build confidence, set goals, and create a balanced lifestyle that aligns with your aspirations.' },
  { title: 'Marriage Consulting', content: 'Get expert advice on marriage and relationships. We offer professional insights and practical solutions to strengthen your relationship and improve communication with your partner.' }
]);

const toggle = (index) => {
  activeIndex.value = activeIndex.value === index ? null : index;
};
</script>

<style>
body {
  background-color: #f8f8f8;
}
</style>
