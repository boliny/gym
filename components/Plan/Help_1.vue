<template>
  <section class="bg-gradient-to-b from-blue-900 to-purple-900 py-20 text-white">
    <div class="max-w-5xl mx-auto text-center px-4">
      <h2 class="text-3xl font-bold uppercase">I Can Help You With</h2>
      <p class="text-gray-300 mt-2">Most frequent questions and answers</p>
    </div>
    
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mt-10 max-w-5xl mx-auto px-4">
      <!-- First row -->
      <div class="border border-white flex items-center justify-center text-6xl p-6">
        <font-awesome-icon :icon="['fas', 'rocket']" />
      </div>
      <div class="flex flex-col items-center justify-center p-6 text-center">
        <h3 class="text-xl font-semibold">1:1 Coaching</h3>
        <p class="text-gray-300 mt-2">Guidance to help you reach your full potential.</p>
        <a href="#" class="mt-4 inline-block transform transition duration-300 hover:scale-105 text-blue-300">READ MORE</a>
      </div>
      <div class="border border-white flex items-center justify-center text-6xl p-6">
        <font-awesome-icon :icon="['fas', 'trophy']" />
      </div>
      
      <!-- Second row -->
      <div class="flex flex-col items-center justify-center p-6 text-center">
        <h3 class="text-xl font-semibold">Self Development</h3>
        <p class="text-gray-300 mt-2">Helping you grow and develop new skills.</p>
        <a href="#" class="mt-4 inline-block transform transition duration-300 hover:scale-105 text-blue-300">READ MORE</a>
      </div>
      <div class="border border-white flex items-center justify-center text-6xl p-6">
        <font-awesome-icon :icon="['fas', 'book']" />
      </div>
      <div class="flex flex-col items-center justify-center p-6 text-center">
        <h3 class="text-xl font-semibold">Life Programs</h3>
        <p class="text-gray-300 mt-2">Structured programs for personal growth.</p>
        <a href="#" class="mt-4 inline-block transform transition duration-300 hover:scale-105 text-blue-300">READ MORE</a>
      </div>
    </div>
  </section>
</template>

<script>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { library } from "@fortawesome/fontawesome-svg-core";
import { faRocket, faTrophy, faBook } from "@fortawesome/free-solid-svg-icons";

library.add(faRocket, faTrophy, faBook);

export default {
  components: {
    FontAwesomeIcon
  }
};
</script>

<style>
body {
  font-family: 'Inter', sans-serif;
}
</style>