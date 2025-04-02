<template>
  <div ref="stepItem" class="relative flex items-start mb-12 last:mb-0 ">
    <!-- الخط الرأسي -->
    <div v-if="!hideSection" class="absolute left-[40px] top-30 w-1 transition-colors duration-500"
      :class="isVisible ? 'bg-emerald-500' : 'bg-gray-300'"
      :style="{ height: isLastStep ? '50%' : '120%', bottom: isLastStep ? 'auto' : '0' }">
    </div>
 
    <!-- الدائرة -->
    <div class="w-20 h-20 flex items-center justify-center rounded-full text-lg font-bold  absolute left-0 top-[50px]  lg:top-[85px]  transition-colors duration-500"
      :class="isVisible ? 'bg-emerald-500 text-white border-emerald-500' : 'bg-gray-200 text-gray-500 border-gray-300'">
      {{ number }}
    </div>

    <!-- البطاقة -->
    <div class="left-26 top-4 lg:p-12 p-6  rounded-lg shadow-md lg:w-full w-3/4 flex items-center justify-between relative text-base transition-colors duration-500 "
      :class="isVisible ? 'bg-emerald-500 text-white' : 'bg-white text-gray-800'">
      <!-- سهم على اليسار -->
      <div class="absolute top-1/2 left-[-6px] w-6 h-6 transform -translate-y-1/2 rotate-45 transition-colors duration-500 "
        :class="isVisible ? 'bg-emerald-500' : 'bg-white'">
      </div>
      <div>
        <h4 class="font-bold my-2 text-2xl">{{ title }}</h4>
        <p>{{ text }}</p>
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