<template>
  <div class="flex flex-col justify-between bg-gradient-to-r from-blue-500 via-purple-600 to-indigo-900 text-white items-center p-6 md:p-12">
    <div class="container grid grid-cols-1 md:grid-cols-2 gap-8 items-center w-full max-w-6xl">
      
      <!-- Image Section (Moves from bottom to top) -->
      <div class="animate-slide-up-slow max-w-[90%] flex justify-center">
        <img src="/public/pngegg.png" alt="Gym" class="w-3/4 sm:w-2/3 md:w-full max-w-xs sm:max-w-sm md:max-w-md lg:max-w-lg object-cover rounded-lg shadow-lg">
      </div>

      <!-- Content Section -->
      <div class="text-center md:text-left animate-fade-in-up">
        <h1 class="text-4xl sm:text-5xl md:text-6xl font-extrabold leading-tight mb-4">
          {{ title }}
        </h1>
        <p class="text-base sm:text-lg md:text-xl text-gray-200 mb-6">
          {{ subtitle }}
        </p>
        <button class="bg-amber-400 hover:bg-amber-500 font-bold py-3 px-6 rounded-lg text-lg shadow-lg transform hover:scale-105 transition duration-300 cursor-pointer">
          {{ buttonText }}
        </button>
        <div class="mt-10 flex flex-wrap justify-center md:justify-start space-x-2 md:space-x-4">
          <span
            v-for="(brand, index) in featuredIn"
            :key="index"
            class="text-gray-300 text-sm sm:text-base md:text-lg animate-fade-in-seq"
            :style="{ animationDelay: index * 0.2 + 's' }"
          >
            {{ brand }}
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "TRANSFORM YOUR BODY & MIND",
      subtitle: "Join our elite gym and start your fitness journey today!",
      buttonText: "Get Started",
      featuredIn: ["Men's Fitness", "FitLife", "Strong Nation", "Health Hub"],
    };
  },
};
</script>

<style>
@keyframes fadeInSequentially {
  from {
    opacity: 0;
    transform: translateY(40px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in-seq {
  animation: fadeInSequentially 1.2s ease-out forwards;
  opacity: 0; /* يبدأ مخفيًا حتى يظهر بالأنيميشن */
}

@keyframes slideUpSlow {
  from {
    opacity: 0;
    transform: translateY(100%);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in-up {
  animation: fadeInUp 1.2s ease-out;
}

.animate-slide-up-slow {
  animation: slideUpSlow 2s ease-out;
}
</style>
