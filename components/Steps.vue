<template>
  <div class="bg-beige">
    <div class="container grid grid-cols-2 mx-auto p-15 items-center  ">
          <!-- القسم الأيسر -->
    <div class="max-w-md text-left">
      <span class="bg-lime-200 text-black px-3 py-1 rounded font-semibold">How it works?</span>
      <h2 class="text-5xl font-bold mt-4">SIMPLE STEPS TO SUCCESS</h2>
      <p class="text-gray-500 mt-2 text-lg">It all starts with a single first step.</p>
    </div>
    

    <!-- القسم الأيمن -->
    <div class="relative flex flex-col  max-w-3xl w-full">
      <StepItem number="1" title="Make a decision" text="Take your first step with confidence and believe in your choice. Your journey starts now!" />
      <StepItem number="2" title="Schedule a meeting" text="Set up a time to discuss your goals and strategies. Planning ahead ensures clarity and direction." />
      <StepItem number="3" title="Show Commitment" text="Stay dedicated to the process and keep pushing forward. Consistency leads to progress." />
      <StepItem number="4" title="Transformation Completed" text="Celebrate your success and reflect on your growth. The journey has made you stronger and wiser." />
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

<style>
.bg-beige { background-color: #FDF8EE; }
</style>
