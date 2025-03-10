<template>
  <div ref="stepItem" class="relative flex items-start mb-10  ">
    <!-- الخط الرأسي -->
    <div class="absolute h-[250px]  w-1 left-[-15px] top-[50px] bottom-0 transition-colors duration-500" 
      :class="isVisible ? 'bg-green-500' : 'bg-gray-300'"></div>
    
    <!-- الدائرة -->
    <div class="w-18 h-18 flex items-center justify-center rounded-full  text-lg font-bold absolute top-[20px] left-[-50px] transform transition-colors duration-500" 
      :class="isVisible ? 'bg-green-500 border-green-500 text-white' : 'bg-gray-200 border-gray-300 text-gray-500'">
      {{ number }}
    </div>
    
    <!-- البطاقة -->
    <div class="ml-16 p-6 rounded-lg shadow-lg w-96 flex items-center justify-between relative text-lg transition-colors duration-500" 
      :class="isVisible ? 'bg-green-500 text-white' : 'bg-white text-gray-800'">
      <!-- سهم على اليسار -->
      <div class="absolute top-[40%] left-[-12px] w-6 h-6 transform rotate-45  transition-colors duration-500" 
        :class="isVisible ? 'bg-green-500 border-green-500' : 'bg-white border-gray-300'"></div>
      <div>
        <h4 class="font-semibold">{{ title }}</h4>
        <p class="text-sm">{{ text }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const props = defineProps({
  number: String,
  title: String,
  text: String
});

const stepItem = ref(null);
const isVisible = ref(false);

const checkVisibility = () => {
  if (stepItem.value) {
    const rect = stepItem.value.getBoundingClientRect();
    isVisible.value = rect.top >= 150 && rect.bottom <= window.innerHeight;
  }
};

onMounted(() => {
  window.addEventListener('scroll', checkVisibility);
  checkVisibility();
});

onUnmounted(() => {
  window.removeEventListener('scroll', checkVisibility);
});
</script>
