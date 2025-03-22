<template>
  <section class="py-16 bg-gray-100 text-center flex justify-center items-center">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl font-bold text-gray-900">I CAN HELP YOU WITH</h2>
      <p class="text-gray-500 mt-2">Most frequent questions and answers</p>

      <div class="grid md:grid-cols-3 gap-12 mt-8 justify-center">
        <div 
          v-for="(item, index) in services" 
          :key="index" 
          class="p-8 flex flex-col items-center border-2 border-gray-300 rounded-lg bg-white shadow-md transition-all duration-300 hover:border-sky-500 min-h-64 max-w-lg mx-auto"
        >
          <!-- أيقونة مع تأثير Scale -->
          <i :class="item.icon" class="text-5xl text-gray-800 mb-4 transition-transform duration-300 transform hover:scale-110"></i>
          
          <h3 class="text-xl font-bold text-gray-900">{{ item.title }}</h3>
          <p class="text-gray-500 mt-3 text-base text-center">{{ item.description }}</p>
          
          <a href="#" class="mt-6 inline-block text-black font-semibold border-b-2 border-black transition-transform duration-300 transform hover:scale-110">
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
    description: "Magnetized strongly enough pre vending domain overeus all initial results to estimate...",
    icon: "fas fa-user"
  },
  {
    title: "PERSONAL DEVELOPMENT",
    description: "Magnetized strongly enough pre vending domain overeus all initial results to estimate...",
    icon: "fas fa-brain"
  },
  {
    title: "LIFE PROGRAMS",
    description: "Magnetized strongly enough pre vending domain overeus all initial results to estimate...",
    icon: "fas fa-life-ring"
  }
];
</script>
