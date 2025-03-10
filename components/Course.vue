<template>
  <div class="bg-cream py-10">
    <h2 class="text-center text-2xl md:text-3xl font-bold mb-6">Courses</h2>
    
    <div class="relative max-w-5xl mx-auto">
      <div ref="sliderRef" class="keen-slider">
        <div v-for="(course, index) in courses" :key="index" class="keen-slider__slide bg-white  shadow-md overflow-hidden border border-gray-200">
          <img :src="course.image" class="w-full h-48 object-cover" />
          <div class="p-6">
            <p class="text-green-400 font-bold">{{ course.price }}</p>
            <h3 class="text-lg font-semibold mt-2">{{ course.title }}</h3>
            <p class="text-sm text-gray-300 mt-1">{{ course.date }}</p>
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
    let sliderInstance = null;
    const courses = [
      {
        title: "GETTING RESULTS: BECOME YOUR OWN LIFE COACH IN 21 DAYS",
        price: "$59",
        date: "May 8, 2018",
        image: "https://via.placeholder.com/300x200/FF5733/FFFFFF?text=Course+1",
      },
      {
        title: "DISCOVER YOURSELF: VALUES, STRENGTHS, VISION, EQ, AND MORE",
        price: "$0",
        date: "September 12, 2018",
        image: "https://via.placeholder.com/300x200/900C3F/FFFFFF?text=Course+2",
      },
      {
        title: "PERSUASION MASTERCLASS: HOW TO POWERFULLY INFLUENCE ANYONE",
        price: "$39",
        date: "September 10, 2018",
        image: "https://via.placeholder.com/300x200/581845/FFFFFF?text=Course+3",
      },
      {
        title: "LEADERSHIP SKILLS: BECOME A CONFIDENT & SUCCESSFUL LEADER",
        price: "$49",
        date: "December 15, 2019",
        image: "https://via.placeholder.com/300x200/1D8348/FFFFFF?text=Course+4",
      },
    ];

    onMounted(() => {
      sliderInstance = new KeenSlider(sliderRef.value, {
        loop: true,
        slides: { perView: 3, spacing: 20 }
      });
    });

    const prevSlide = () => sliderInstance.prev();
    const nextSlide = () => sliderInstance.next();

    return { courses, prevSlide, nextSlide, sliderRef };
  }
};
</script>

<style>
.bg-cream {
  background-color: #f5e6ca;
}
</style>
