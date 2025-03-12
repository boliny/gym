<template>
  <div ref="stepItem" class="relative flex items-start mb-12 last:mb-0">
    <!-- الخط الرأسي -->
    <div v-if="!hideSection" class="absolute left-[-15px] top-20 w-1 transition-colors duration-500"
      :class="isVisible ? 'bg-emerald-500' : 'bg-gray-300'"
      :style="{ height: isLastStep ? '50%' : '120%', bottom: isLastStep ? 'auto' : '0' }">
    </div>

    <!-- الدائرة -->
    <div class="w-18 h-18 flex items-center justify-center rounded-full text-lg font-bold border-4 absolute left-[-50px] top-[60px] transition-colors duration-500"
      :class="isVisible ? 'bg-emerald-500 text-white border-emerald-500' : 'bg-gray-200 text-gray-500 border-gray-300'">
      {{ number }}
    </div>

    <!-- البطاقة -->
    <div class="ml-16 p-6 rounded-lg shadow-lg w-full max-w-md flex items-center justify-between relative text-lg transition-colors duration-500"
      :class="isVisible ? 'bg-emerald-500 text-white' : 'bg-white text-gray-800'">
      <!-- سهم على اليسار -->
      <div class="absolute top-1/2 left-[-10px] w-5 h-5 transform -translate-y-1/2 rotate-45 transition-colors duration-500"
        :class="isVisible ? 'bg-emerald-500' : 'bg-white border border-gray-300'"></div>
      <div>
        <h4 class="font-bold my-4">{{ title }}</h4>
        <p class="">{{ text }}</p>
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
  hideSection: Boolean // تجعل الخط يتوقف عند آخر خطوة
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
/* تحسين التنسيق للأجهزة الصغيرة */
@media (max-width: 640px) {
  .relative {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }
  .ml-16 {
    margin-left: 0;
  }
  .absolute.left-0 {
    left: 50%;
    transform: translateX(-50%);
  }
  .absolute.left-6 {
    left: 50%;
    transform: translateX(-50%);
  }
  .absolute.left- {
    left: 50%;
    transform: translateX(-50%);
  }
}
</style>
