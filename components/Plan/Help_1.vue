<template>
  <section class="bg-gradient-to-b from-blue-900 to-purple-900 py-20 text-white">
    <div class="max-w-5xl mx-auto text-center">
      <h2 class="text-3xl font-bold uppercase">I Can Help You With</h2>
      <p class="text-gray-300 mt-2">Most frequent questions and answers</p>
    </div>
    <div class="grid grid-cols-3 grid-rows-2 gap-0 mt-10 max-w-5xl mx-auto">
      <!-- First row -->
      <div class="border border-white flex items-center justify-center text-6xl">🚀</div>
      <div class="border border-white flex flex-col items-center justify-center p-6 text-center">
        <h3 class="text-xl font-semibold">1:1 Coaching</h3>
        <p class="text-gray-300 mt-2">Magnetized strongly enough pre vending domain overeus all initial results to estimate the in the big bang contradicted.</p>
        <a href="#" class="mt-4 inline-block transform transition duration-300 hover:scale-105">READ MORE</a>
      </div>
      <div class="border border-white flex items-center justify-center text-6xl">🏆</div>
      
      <!-- Second row -->
      <div class="border border-white flex flex-col items-center justify-center p-6 text-center">
        <h3 class="text-xl font-semibold">Self Development</h3>
        <p class="text-gray-300 mt-2">Magnetized strongly enough pre vending domain overeus all initial results to estimate the in the big bang contradicted.</p>
        <a href="#" class="mt-4 inline-block transform transition duration-300 hover:scale-105">READ MORE</a>
      </div>
      <div class="border border-white flex items-center justify-center text-6xl">📖</div>
      <div class="border border-white flex flex-col items-center justify-center p-6 text-center">
        <h3 class="text-xl font-semibold">Life Programs</h3>
        <p class="text-gray-300 mt-2">Magnetized strongly enough pre vending domain overeus all initial results to estimate the in the big bang contradicted.</p>
        <a href="#" class="mt-4 inline-block transform transition duration-300 hover:scale-105">READ MORE</a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      services: [
        { title: "1:1 Coaching", icon: "🚀", description: "Magnetized strongly enough pre vending domain overeus all initial results to estimate the in the big bang contradicted." },
        { title: "Self Development", icon: "📖", description: "Magnetized strongly enough pre vending domain overeus all initial results to estimate the in the big bang contradicted." },
        { title: "Life Programs", icon: "🏆", description: "Magnetized strongly enough pre vending domain overeus all initial results to estimate the in the big bang contradicted." }
      ]
    };
  }
};
</script>

<style>
body {
  font-family: 'Inter', sans-serif;
}
</style>
