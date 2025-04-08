<template>
  <div ref="stepsSection" class="relative w-full py-16 bg-gray-100 flex justify-center overflow-x-hidden">
    <div class="absolute left-1/2 transform -translate-x-1/2 w-1 bg-gray-300 rounded-full overflow-hidden"
      :style="{ top: `${progressStart}%`, height: `${progressEnd - progressStart}%` }">
      <div class="absolute top-0 w-full bg-sky-400 progress-bar rounded-full" :style="{ height: `${sectionProgress}%` }"></div>
      <div 
        v-for="(step, index) in steps" 
        :key="index" 
        class="absolute flex items-center justify-center w-8 h-8 bg-white border-4 border-gray-400 rounded-full transition-all duration-300"
        :class="{ 'border-sky-400 text-sky-400': sectionProgress >= (index + 1) * (100 / steps.length) }"
        :style="{ top: `${(index + 1) * (100 / steps.length)}%`, left: '50%', transform: 'translate(-50%, -50%)' }"
      >
        <font-awesome-icon :icon="['fas', step.icon]" class="text-lg" />
      </div>
    </div>

    <div class="container mx-auto flex flex-col space-y-12 px-4 sm:px-8 md:px-16 lg:px-24 relative">
      <StepCard 
        v-for="(step, index) in steps" 
        :key="index" 
        :title="step.title" 
        :description="step.description" 
        :icon="step.icon" 
        :index="index"
        :position="index % 2 === 0 ? 'left' : 'right'"
        :class="{'-ml-10': index === steps.length - 1}"
        class="opacity-0 step-card will-change-transform"
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
      { title: "Step 1: Start Your Journey", description: "Every journey begins with a single step.", icon: "flag" },
      { title: "Step 2: Plan Your Actions", description: "Set a clear plan and strategy.", icon: "clipboard-list" },
      { title: "Step 3: Execute & Adapt", description: "Take action and adjust when necessary.", icon: "play-circle" },
      { title: "Step 4: Reach Your Goals", description: "Celebrate your success and set new milestones.", icon: "trophy" }
    ]);

    const sectionProgress = ref(0);
    const stepsSection = ref(null);
    const progressStart = ref(15);
    const progressEnd = ref(85);

    const updateScroll = () => {
      if (!stepsSection.value) return;
      const sectionTop = stepsSection.value.getBoundingClientRect().top + window.scrollY;
      const sectionBottom = sectionTop + stepsSection.value.clientHeight;
      const scrollY = window.scrollY + window.innerHeight / 10;
      
      sectionProgress.value = scrollY < sectionTop ? 0 : scrollY > sectionBottom ? 100 : ((scrollY - sectionTop) / (sectionBottom - sectionTop)) * 100;
    };

    onMounted(() => {
      window.addEventListener('scroll', updateScroll);
      document.body.style.overflowX = 'hidden';
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

    return { steps, sectionProgress, stepsSection, progressStart, progressEnd };
  }
};
</script>

<style>
.progress-bar {
  transition: height 0.3s ease-out;
}

.step-card {
  opacity: 0;
  transform: translateX(-50px);
  max-width: 90%;
}
</style>
