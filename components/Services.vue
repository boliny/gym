<template>
  <div class="bg-light-blue py-10">
    <h2 class="text-center text-2xl md:text-3xl font-bold mb-6">RESULTS I HAVE HELPED CREATE</h2>

    <div class="relative max-w-5xl mx-auto">
      <div ref="sliderRef" class="keen-slider">
        <div v-for="(testimonial, index) in testimonials" :key="index" class="keen-slider__slide card">
          <div class="max-w-md mx-auto bg-white rounded-xl shadow-md p-8 border border-gray-200 text-center">
            <div class="flex justify-center mb-3">
              <svg v-for="star in 5" :key="star" class="w-6 h-6 text-yellow-500" fill="currentColor" viewBox="0 0 20 20">
                <path d="M10 15.27L16.18 19l-1.64-7.03L19 7.24l-7.19-.61L10 0 8.19 6.63 1 7.24l5.46 4.73L4.82 19z"></path>
              </svg>
            </div>
            <p class="text-gray-700 text-base italic leading-relaxed line-clamp-6">"{{ testimonial.text }}"</p>
            <div class="mt-4 flex justify-center">
              <img :src="testimonial.image" class="w-20 h-20 rounded-full border-2 border-gray-300" />
            </div>
            <h3 class="mt-3 text-lg font-semibold text-gray-900">{{ testimonial.name }}</h3>
            <p class="text-blue-500 text-sm">{{ testimonial.role }}</p>
          </div>
        </div>
      </div>

      <button @click="prevSlide" class="prev-btn absolute left-[-80px] top-1/2 transform -translate-y-1/2 w-12 h-12 bg-white rounded-full shadow flex items-center justify-center cursor-pointer">
        <svg class="w-7 h-7 text-gray-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" d="M15 19l-7-7 7-7"></path>
        </svg>
      </button>

      <button @click="nextSlide" class="next-btn absolute right-[-80px] top-1/2 transform -translate-y-1/2 w-12 h-12 bg-white rounded-full shadow flex items-center justify-center cursor-pointer">
        <svg class="w-7 h-7 text-gray-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7"></path>
        </svg>
      </button>

      <div class="pagination flex justify-center mt-4">
        <div v-for="(_, index) in testimonials.length" :key="index" @click="moveToSlide(index)" 
          :class="['dot', { active: currentSlide === index }]" 
          class="w-4 h-4 mx-1 bg-gray-300 rounded-full cursor-pointer transition-all hover:bg-gray-500"></div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref, onMounted } from "vue";
import KeenSlider from "keen-slider";
import "keen-slider/keen-slider.min.css";

export default {
  setup() {
    const sliderRef = ref(null);
    const slider = ref(null);
    const currentSlide = ref(0);
    
    onMounted(() => {
      slider.value = new KeenSlider(sliderRef.value, {
        loop: true,
        slides: { perView: 3, spacing: 20 },
        created(s) { currentSlide.value = s.track.details.rel; },
        slideChanged(s) { currentSlide.value = s.track.details.rel; }
      });
    });

    const prevSlide = () => slider.value.moveToIdx(slider.value.track.details.rel - 1, true);
    const nextSlide = () => slider.value.moveToIdx(slider.value.track.details.rel + 1, true);
    const moveToSlide = (index) => slider.value.moveToIdx(index, true);
    
    return {
      sliderRef,
      currentSlide,
      prevSlide,
      nextSlide,
      moveToSlide,
      testimonials: [
        { text: "This service helped me grow my business tremendously! I've never seen such great results before, and I am truly impressed with the level of support and features provided.", name: "Alice Johnson", role: "Marketing Manager", image: "https://randomuser.me/api/portraits/women/1.jpg" },
        { text: "The best decision I ever made was using this platform. It has completely transformed my workflow and made things so much easier!", name: "Michael Smith", role: "Entrepreneur", image: "https://randomuser.me/api/portraits/men/2.jpg" },
        { text: "Highly recommended for anyone looking to improve! The quality of service is outstanding, and the features are exactly what I needed.", name: "Sophia Brown", role: "Designer", image: "https://randomuser.me/api/portraits/women/3.jpg" },
        { text: "Great experience, I will definitely use this again! The team is very responsive, and the platform is incredibly easy to use.", name: "David Lee", role: "Developer", image: "https://randomuser.me/api/portraits/men/4.jpg" },
        { text: "Absolutely fantastic service! I couldn't be happier with the results. Highly efficient and worth every penny!", name: "Emma Wilson", role: "Photographer", image: "https://randomuser.me/api/portraits/women/5.jpg" },
        { text: "A game changer for my business! This service has allowed me to scale like never before, and I am beyond satisfied.", name: "John Doe", role: "Business Owner", image: "https://randomuser.me/api/portraits/men/6.jpg" }
      ]
    };
  }
};
</script>

<style>
.bg-light-blue {
  background-color: #e3f2fd;
}
.pagination .dot {
  transition: all 0.5s linear;
  width: 10px;
  height: 10px;
}
.pagination .dot:hover {
  background-color: #838c93;
}
.pagination .dot.active {
  background-color: #007bff;
  width: 12px;
  height: 12px;
}
.pagination .dot.active:hover {
  background-color: #004289;
}
</style>
