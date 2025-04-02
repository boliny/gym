<template>
  <div :class="['step-card', position === 'left' ? 'ml-auto' : 'mr-auto']">
    <div class="relative bg-white shadow-lg rounded-lg p-8 w-full max-w-md flex items-center">
      <div class="mr-2 text-sky-500 text-3xl">
        <font-awesome-icon :icon="icon" />
      </div>
      <div>
        <h3 class="text-2xl font-bold text-gray-800">{{ title }}</h3>
        <p class="text-gray-600 mt-2">{{ description }}</p>
      </div>
      <div class="absolute top-1/2 transform -translate-y-1/2 w-0 h-0 border-10 border-transparent"
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
  transition: opacity 0.5s ease-out, transform 0.5s ease-out;
}
</style>
