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
        </div>

        <!-- القسم الأيمن (خطوات) -->
        <div class="relative flex flex-col max-w-lg mx-auto w-full">
          <StepItem number="1" title="Make a decision" text="Take your first step with confidence and believe in your choice. Your journey starts now!" />
          <StepItem number="2" title="Schedule a meeting" text="Set up a time to discuss your goals and strategies. Planning ahead ensures clarity and direction." />
          <StepItem number="3" title="Show Commitment" text="Stay dedicated to the process and keep pushing forward. Consistency leads to progress." />
          <StepItem number="4" title="Transformation Completed" text="Celebrate your success and reflect on your growth. The journey has made you stronger and wiser." />
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

<style>
.bg-beige {
  background-color: #FDF8EE;
}
</style>
