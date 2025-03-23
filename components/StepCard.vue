<template>
  <div   :class="['step-card', position === 'left' ? 'ml-auto' : 'mr-auto']">
    <div class="relative bg-white shadow-lg rounded-lg p-8 w-[500px] flex items-center">
      <div class="mr-4 text-sky-400 text-3xl">
        <font-awesome-icon :icon="icon" />
      </div>
      <div>
        <h3 class="text-2xl font-bold">{{ title }}</h3>
        <p class="text-gray-600 mt-2">{{ description }}</p>
      </div>
      <!-- سهم يشير إلى البار -->
      <div class="absolute top-1/2 transform -translate-y-1/2 w-0 h-0 border-20 border-transparent"
        :class="position === 'left' ? 'right-full border-r-white' : 'left-full border-l-white'">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    description: String,
    icon: String,
    position: String,
  },
};
</script>

<style>
.step-card {
  opacity: 0;
  transform: translateX(-50px);
}
</style>
