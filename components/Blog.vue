<template>
  <div class="bg-cream py-10">
    <h2 class="text-center text-2xl md:text-3xl font-bold mb-6">Blog</h2>

    <div class="relative max-w-5xl mx-auto">
      <div ref="sliderRef" class="keen-slider">
        <div
          v-for="(blog, index) in blogs"
          :key="index"
          class="keen-slider__slide bg-white shadow-md overflow-hidden border border-gray-200"
        >
          <img :src="blog.image" class="w-full h-48 object-cover" />
          <div class="p-6">
            <h3 class="text-lg font-semibold text-gray-900">{{ blog.title }}</h3>
            <a href="#" class="text-blue-500 text-sm font-semibold mt-3 inline-block">Read More</a>
          </div>
        </div>
      </div>

      <!-- الأسهم (مخفية على الشاشات الصغيرة) -->
      <button
        v-if="showNavigation"
        @click="prevSlide"
        class="prev-btn absolute left-[-80px] top-1/2 transform -translate-y-1/2 w-12 h-12 bg-white rounded-full shadow flex items-center justify-center cursor-pointer"
      >
        <svg class="w-7 h-7 text-gray-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" d="M15 19l-7-7 7-7"></path>
        </svg>
      </button>

      <button
        v-if="showNavigation"
        @click="nextSlide"
        class="next-btn absolute right-[-80px] top-1/2 transform -translate-y-1/2 w-12 h-12 bg-white rounded-full shadow flex items-center justify-center cursor-pointer"
      >
        <svg class="w-7 h-7 text-gray-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7"></path>
        </svg>
      </button>
    </div>

    <div class="flex justify-center mt-6">
      <button class="relative cursor-pointer bg-gray-900 px-6 py-3 rounded text-white text-lg font-semibold overflow-hidden group">
        <span class="absolute inset-0 bg-gray-600 transform -translate-x-full transition-all duration-300 group-hover:translate-x-0 flex items-center justify-center">GO TO BLOG</span>
        <span class="relative group-hover:opacity-0">All Posts</span>
      </button>
    </div>
  </div>
</template>

<script>
import { ref, onMounted, onUnmounted } from "vue";
import KeenSlider from "keen-slider";
import "keen-slider/keen-slider.min.css";

export default {
  setup() {
    const sliderRef = ref(null);
    const slider = ref(null);
    const slidesPerView = ref(3);
    const showNavigation = ref(true);

    const updateSliderSettings = () => {
      if (window.innerWidth < 768) {
        slidesPerView.value = 1; // شريحة واحدة على الشاشات الصغيرة
        showNavigation.value = false; // إخفاء الأسهم
      } else {
        slidesPerView.value = 3; // 3 شرائح على الشاشات الكبيرة
        showNavigation.value = true; // إظهار الأسهم
      }

      if (slider.value) {
        slider.value.update({
          loop: true,
          slides: { perView: slidesPerView.value, spacing: 20 },
        });
      }
    };

    onMounted(() => {
      updateSliderSettings(); // تحديث عند التحميل
      slider.value = new KeenSlider(sliderRef.value, {
        loop: true,
        slides: { perView: slidesPerView.value, spacing: 20 },
        created(s) {
          setInterval(() => {
            s.moveToIdx(s.track.details.rel + 1, true);
          }, 3000); // MARKER: تم إضافة التشغيل التلقائي بدون توقف
        }, 
      });

      window.addEventListener("resize", updateSliderSettings);
    });

    onUnmounted(() => {
      window.removeEventListener("resize", updateSliderSettings);
    });

    const prevSlide = () => slider.value.moveToIdx(slider.value.track.details.rel - 1, true);
    const nextSlide = () => slider.value.moveToIdx(slider.value.track.details.rel + 1, true);

    return {
      blogs: [
        { image: "https://picsum.photos/400/300?random=1", title: "How to be 1% Better Every Day" },
        { image: "https://picsum.photos/400/300?random=2", title: "5 Habits of Highly Effective People" },
        { image: "https://picsum.photos/400/300?random=3", title: "Why Mindset Matters" },
        { image: "https://picsum.photos/400/300?random=4", title: "Building a Strong Morning Routine" },
        { image: "https://picsum.photos/400/300?random=5", title: "The Power of Gratitude" },
      ],
      sliderRef,
      prevSlide,
      nextSlide,
      showNavigation,
    };
  },
};
</script>

<style>
.bg-cream {
  background-color: #f5e6ca;
}
</style>
