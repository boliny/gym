<template>
  <div ref="stepItem" class="relative flex items-start mb-12 last:mb-0 lg:flex-col lg:items-center lg:text-center">
    <!-- الخط الرأسي -->
    <div v-if="!hideSection" class="absolute left-[-10px] top-20 w-1 transition-colors duration-500 lg:left-1/2 lg:-translate-x-1/2"
      :class="isVisible ? 'bg-emerald-500' : 'bg-gray-300'"
      :style="{ height: isLastStep ? '50%' : '120%', bottom: isLastStep ? 'auto' : '0' }">
    </div>

    <!-- الدائرة -->
    <div class="w-16 h-16 flex items-center justify-center rounded-full text-lg font-bold border-4 absolute left-[-45px] top-[40px] transition-colors duration-500 lg:relative lg:left-auto lg:top-auto lg:mb-4"
      :class="isVisible ? 'bg-emerald-500 text-white border-emerald-500' : 'bg-gray-200 text-gray-500 border-gray-300'">
      {{ number }}
    </div>

    <!-- البطاقة -->
    <div class="ml-12 p-3 rounded-lg shadow-md w-full max-w-sm flex items-center justify-between relative text-base transition-colors duration-500 lg:ml-0 lg:flex-col lg:items-center"
      :class="isVisible ? 'bg-emerald-500 text-white' : 'bg-white text-gray-800'">
      <!-- سهم على اليسار -->
      <div class="absolute top-1/2 left-[-6px] w-4 h-4 transform -translate-y-1/2 rotate-45 transition-colors duration-500 lg:left-1/2 lg:-translate-x-1/2 lg:top-[-6px]"
        :class="isVisible ? 'bg-emerald-500' : 'bg-white'">
      </div>
      <div>
        <h4 class="font-bold my-2 text-base">{{ title }}</h4>
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
  text: String,
  isLastStep: Boolean,
  hideSection: Boolean 
});

const stepItem = ref(null);
const isVisible = ref(false);

const checkVisibility = () => {
  if (stepItem.value) {
    const rect = stepItem.value.getBoundingClientRect();
    const windowHeight = window.innerHeight || document.documentElement.clientHeight;
    isVisible.value = rect.top < windowHeight * 0.3 && rect.bottom > 0;
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

<style scoped>
@media (min-width: 1024px) {
  .relative {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }
  .ml-12 {
    margin-left: 0;
  }
  .circle-wrapper {
    position: relative;
    left: auto;
    top: auto;
    margin-bottom: 8px;
  }
}
</style> 