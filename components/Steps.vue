<template>
  <div class="bg-beige py-12">
    <div class="container mx-auto px-6 md:px-12 lg:px-20">
      <!-- الشبكة المتجاوبة -->
      <div class="grid grid-cols-1 md:grid-cols-2 gap-10 items-center">
        
        <!-- القسم الأيسر -->
        <div class="text-center md:text-left max-w-md mx-auto">
          <span class="bg-lime-200 text-black px-3 py-1 rounded font-semibold text-sm md:text-base">How it works?</span>
          <h2 class="text-3xl md:text-5xl font-bold mt-4 leading-tight">SIMPLE STEPS TO SUCCESS</h2>
          <p class="text-gray-500 mt-2 text-lg">It all starts with a single first step.</p>
          <p class="mt-10 text-gray-500">Learn about how them you went down prying the wedding ring off his cold, dead finger. I don’t know what you did, Fry, but once again, you screwed up! Now all the planets are gonna start cracking wise about our mamas.</p>
        </div>

        <!-- القسم الأيمن (خطوات) -->
        <div class="relative flex flex-col  mx-auto w-full">
          
          <StepItem number="1" title="Make a decision" text="Lorem ipsum dolor sit amet, mea ei viderer probatus consequuntur, sonet vocibus lobortis has ad." />
          <StepItem number="2" title="Schedule a meeting" text="Lorem ipsum dolor sit amet, mea ei viderer probatus consequuntur, sonet vocibus lobortis has ad." />
          <StepItem number="3" title="Show Commitment" text="Lorem ipsum dolor sit amet, mea ei viderer probatus consequuntur, sonet vocibus lobortis has ad." />
          <StepItem :hideSection="true"  number="4" title="Transformation Completed" text="Lorem ipsum dolor sit amet, mea ei viderer probatus consequuntur, sonet vocibus lobortis has ad." />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import StepItem from "@/components/StepItem.vue";

export default {
  components: {
    StepItem,
  },
};
</script>

<style scoped>
.bg-beige {
  background-color: #FDF8EE;
}

.step-container {
  display: flex;
  align-items: flex-start;
  position: relative;
}

.step-circle {
  width: 28px;
  height: 28px;
  background-color: #4CAF50;
  border: 4px solid white;
  border-radius: 50%;
  position: absolute;
  left: -14px;
  top: 6px;
}

.step-line {
  position: absolute;
  left: 10px;
  top: 34px;
  width: 2px;
  height: 100%;
  background-color: #ccc;
}
</style>
