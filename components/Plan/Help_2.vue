<template>
  <section class="flex flex-col items-center text-center py-16 px-8 bg-gray-100">
    <h2 class="text-4xl font-bold mb-4 text-gray-800">I CAN HELP YOU WITH</h2>
    <p class="text-gray-600 mb-12">Most frequent questions and answers</p>

    <div class="relative flex flex-wrap justify-center items-center max-w-6xl mx-auto">
      <!-- Enlarged Image in the Center -->
      <div class="relative w-96 h-96 rounded-full overflow-hidden shadow-xl">
        <img src="https://themes.pixelwars.org/efor/demo-04/wp-content/uploads/sites/6/2018/09/011-550x362.jpg" alt="Person" class="w-full h-full object-cover">
      </div>
      
      <!-- Items -->
      <div class="absolute top-0 left-[-300px] flex flex-col items-center w-48 text-center text-gray-800">
        <i class="fas fa-user text-3xl mb-3"></i>
        <h3 class="font-bold text-lg">1:1 COACHING</h3>
        <p class="text-sm text-gray-500">Personalized coaching to help you succeed.</p>
      </div>
      
      <div class="absolute top-0 right-[-300px] flex flex-col items-center w-48 text-center text-gray-800">
        <i class="fas fa-cube text-3xl mb-3"></i>
        <h3 class="font-bold text-lg">SELF DEVELOPMENT</h3>
        <p class="text-sm text-gray-500">Grow and develop your skills effectively.</p>
      </div>
      
      <div class="absolute bottom-0 left-[-300px] flex flex-col items-center w-48 text-center text-gray-800">
        <i class="fas fa-bullseye text-3xl mb-3"></i>
        <h3 class="font-bold text-lg">LIFE PROGRAMS</h3>
        <p class="text-sm text-gray-500">Programs designed for better life management.</p>
      </div>
      
      <div class="absolute bottom-0 right-[-300px] flex flex-col items-center w-48 text-center text-gray-800">
        <i class="fas fa-leaf text-3xl mb-3"></i>
        <h3 class="font-bold text-lg">SUPPORT</h3>
        <p class="text-sm text-gray-500">Ongoing support to ensure your progress.</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
};
</script>


