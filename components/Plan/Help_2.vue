<template>
  <section class="flex flex-col items-center text-center py-16 px-8 bg-gray-100">
    <h2 class="text-4xl font-bold mb-4 text-gray-800">I CAN HELP YOU WITH</h2>
    <p class="text-gray-600 mb-12">Most frequent questions and answers</p>

    <div class="flex flex-col md:flex-row md:flex-wrap justify-center items-center max-w-6xl mx-auto gap-8">
      <!-- Enlarged Image in the Center -->
      <div class="w-64 h-64 md:w-80 md:h-80 lg:w-96 lg:h-96 rounded-full overflow-hidden shadow-xl">
        <img
          src="https://themes.pixelwars.org/efor/demo-04/wp-content/uploads/sites/6/2018/09/011-550x362.jpg"
          alt="Person"
          class="w-full h-full object-cover"
        />
      </div>

      <!-- Items Grid -->
      <div class="grid grid-cols-1 sm:grid-cols-2 gap-6 text-gray-800 text-center">
        <div class="flex flex-col items-center">
          <i class="fas fa-user text-3xl mb-3"></i>
          <h3 class="font-bold text-lg">1:1 COACHING</h3>
          <p class="text-sm text-gray-500">Personalized coaching to help you succeed.</p>
        </div>

        <div class="flex flex-col items-center">
          <i class="fas fa-cube text-3xl mb-3"></i>
          <h3 class="font-bold text-lg">SELF DEVELOPMENT</h3>
          <p class="text-sm text-gray-500">Grow and develop your skills effectively.</p>
        </div>

        <div class="flex flex-col items-center">
          <i class="fas fa-bullseye text-3xl mb-3"></i>
          <h3 class="font-bold text-lg">LIFE PROGRAMS</h3>
          <p class="text-sm text-gray-500">Programs designed for better life management.</p>
        </div>

        <div class="flex flex-col items-center">
          <i class="fas fa-leaf text-3xl mb-3"></i>
          <h3 class="font-bold text-lg">SUPPORT</h3>
          <p class="text-sm text-gray-500">Ongoing support to ensure your progress.</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {};
</script>
