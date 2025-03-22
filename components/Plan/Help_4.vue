<template>
  <section class="py-16 bg-gray-100 text-center flex justify-center items-center">
    <div class="container mx-auto">
      <h2 class="text-3xl font-bold text-gray-900">I CAN HELP YOU WITH</h2>
      <p class="text-gray-500 mt-2">Most frequent questions and answers</p>

      <div class="grid md:grid-cols-3 gap-4 mt-8 justify-center">
        <div v-for="(item, index) in services" :key="index" class="p-4">
          <h3 class="text-lg font-bold text-gray-900">{{ item.title }}</h3>
          <p class="text-gray-500 mt-2">{{ item.description }}</p>
          <a href="#" class="mt-4 inline-block text-black font-semibold border-b-2 border-black transition-transform duration-300 transform hover:scale-110">
            READ MORE
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const services = [
  {
    title: "1:1 COACHING",
    description: "Magnetized strongly enough pre vending domain overeus all initial results to estimate..."
  },
  {
    title: "PERSONAL DEVELOPMENT",
    description: "Magnetized strongly enough pre vending domain overeus all initial results to estimate..."
  },
  {
    title: "LIFE PROGRAMS",
    description: "Magnetized strongly enough pre vending domain overeus all initial results to estimate..."
  }
];
</script>
