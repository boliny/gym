<template>
  <div class="hero-section flex flex-col md:flex-row text-white p-6 md:p-8 min-h-[70vh] overflow-hidden">
    
    <!-- Image Section -->
    <div class="image-container">
      <img src="/public/pngegg.png" alt="Gym" class="gym-image  w-full animate-slide-up">
    </div>

    <!-- Content Section -->
    <div class="text-center md:text-left justify-center  px-4 sm:px-6 lg:px-10">
      <p class="my-10 md:my-10 text-lg md:text-xl font-bold animate-fade-in delay-1">Hi, I am Richard Hopkins.</p>
      <h1 class="text-6xl font-extrabold sm:text-xl md:text-4xl leading-tight mb-3 animate-fade-in delay-2">
        {{ title }}
      </h1>
      <p class="text-sm sm:text-base md:text-lg mb-4 animate-fade-in delay-3">
        {{ subtitle }}
      </p>
      <button class="bg-amber-300 hover:bg-amber-500 font-bold text-black py-5 px-15 rounded-lg  shadow-lg transform hover:scale-110 transition duration-300 cursor-pointer animate-fade-in delay-4">
          {{ buttonText }}
      </button>
      
      <!-- Featured In Section -->
      <h3 class=" text-center text-sm sm:text-base font-bold mt-6 animate-fade-in delay-5">FEATURED IN</h3>
      <div class="flex justify-center items-center gap-8 mt-4 flex-wrap">
        <span class="brand-logo animate-fade-in delay-5 text-white text-2xl font-bold">HOLP</span>
        <span class="brand-logo animate-fade-in delay-6 text-white italic text-xl">Feed&Food</span>
        <span class="brand-logo animate-fade-in delay-7 text-white text-2xl font-bold">LA <span class="text-sm">COACH BASE</span></span>
        <span class="brand-logo animate-fade-in delay-8 text-white text-2xl font-bold">Bridgette</span>
        <span class="brand-logo animate-fade-in delay-9 text-white text-2xl font-bold">amazero</span>
        <span class="brand-logo animate-fade-in delay-10 text-white italic text-xl">Vibes</span>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "I HELPED MILLIONS OF PEOPLE TO IMPROVE THEIR LIVES",
      subtitle: "Are you the next? Discover the simple 3 Steps that I Discovered to Hack Productivity. It works 100%. Wanna transform your life?",
      buttonText: "Get Your FREE GUIDE",
    };
  },
};
</script>

<style scoped>
@keyframes fadeInUp {
  0% {
    opacity: 0;
    transform: translateY(30px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes slideUp {
  0% {
    opacity: 0;
    transform: translateY(100%);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes bounceSlow {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-5px); }
}
.hero-section {
  background-image: url('/public/waves.jpg');
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
}
.animate-fade-in {
  opacity: 0;
  animation: fadeInUp 1s ease-out forwards;
}
.animate-slide-up {
  opacity: 0;
  animation: slideUp 1.5s ease-out forwards;
}

.delay-1 { animation-delay: 0.2s; }
.delay-2 { animation-delay: 0.4s; }
.delay-3 { animation-delay: 0.6s; }
.delay-4 { animation-delay: 0.8s; }
.delay-5 { animation-delay: 1s; }
.delay-6 { animation-delay: 1.2s; }
.delay-7 { animation-delay: 1.4s; }
.delay-8 { animation-delay: 1.6s; }
.delay-9 { animation-delay: 1.8s; }
.delay-10 { animation-delay: 2s; }

.animate-bounce-slow {
  animation: bounceSlow 2s infinite;
}

.hero-section {
  overflow: hidden;
}

.image-container {
  width: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}

.gym-image {
  max-width: 500px;
  position: absolute;
  top: 0;
}
@media (max-width: 1024px) {
  .hero-section {
    text-align: center;
  }
  .gym-image {
    max-width: 100%;
    position: relative;
    left: 50%;    
    top: 30px;
  }
}
</style>
