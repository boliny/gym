<template>
  <div ref="stepsSection" class="relative w-full py-16 bg-gray-100 flex justify-center">
    <!-- Progress Bar (عمودي) -->
    <div class="absolute left-1/2 transform -translate-x-1/2 h-full w-2 bg-gray-300 rounded-full overflow-hidden">
      <div class="absolute top-0 w-full h-0 bg-sky-400 progress-bar rounded-full"></div>
      <!-- أيقونات الخطوات -->
      <div 
        v-for="(step, index) in steps" 
        :key="index" 
        class="absolute flex items-center justify-center w-10 h-10 bg-white border-4 border-gray-400 rounded-full transition-all duration-300"
        :class="{ 'border-sky-400 text-sky-400': sectionProgress >= (index + 1) * (100 / steps.length) }"
        :style="{ top: `${(index + 1) * (100 / steps.length)}%`, left: '50%', transform: 'translate(-50%, -50%)' }"
      >
        <font-awesome-icon :icon="step.icon" class="text-xl" />
      </div>
    </div>

    <!-- الكروت -->
    <div class="container mx-auto flex flex-col space-y-16 relative">
      <StepCard 
        v-for="(step, index) in steps" 
        :key="index" 
        :title="step.title" 
        :description="step.description" 
        :icon="step.icon" 
        :index="index"
        :position="index % 2 === 0 ? 'left' : 'right'"
        class="opacity-0"
      />
    </div>
  </div>
</template>

<script>
import { ref, onMounted, onUnmounted, nextTick } from 'vue';
import gsap from 'gsap';
import StepCard from '@/components/StepCard.vue';

export default {
  components: { StepCard },
  setup() {
    const steps = ref([
      { title: "Step 1: You Decide to Improve", description: "Taking the first step toward change is crucial.", icon: "check" },
      { title: "Step 2: Book an Appointment", description: "Find a professional to guide you.", icon: "calendar" },
      { title: "Step 3: Take Action", description: "Execution is key. Follow your plan.", icon: "play" },
      { title: "Step 4: Achieve Your Goals", description: "Stay consistent and celebrate success.", icon: "trophy" }
    ]);

    const sectionProgress = ref(0);
    const stepsSection = ref(null);

    const updateScroll = () => {
      if (!stepsSection.value) return;
      const sectionTop = stepsSection.value.offsetTop;
      const sectionBottom = sectionTop + stepsSection.value.clientHeight;
      const scrollY = window.scrollY + window.innerHeight / 2;
      
      if (scrollY < sectionTop) {
        sectionProgress.value = 0;
      } else if (scrollY > sectionBottom) {
        sectionProgress.value = 100;
      } else {
        sectionProgress.value = ((scrollY - sectionTop) / (sectionBottom - sectionTop)) * 100;
      }
      
      gsap.to(".progress-bar", {
        height: `${sectionProgress.value}%`,
        duration: 0.2,
        ease: "power3.out"
      });
    };

    onMounted(() => {
      window.addEventListener('scroll', updateScroll);
      
      nextTick(() => {
        gsap.to(".step-card", {
          opacity: 1,
          x: 0,
          duration: 1,
          ease: "power3.out",
          stagger: 0.3
        });
      });
    });

    onUnmounted(() => {
      window.removeEventListener('scroll', updateScroll);
    });

    return { steps, sectionProgress, stepsSection };
  }
};
</script>

<style>
.progress-bar {
  transition: height 0.2s ease-out;
}
</style>