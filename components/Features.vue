<template>
  <section class="bg-darkBlue py-20">
    <div class="container mx-auto text-center">
      <p class="text-yellow-400 uppercase text-sm  font-semibold tracking-wide">
        As Featured In
      </p>
      <div class="grid grid-cols-auto-fit  gap-6 sm:gap-8 mt-6">
        <span class="brand-item">HOLP</span>
        <span class="brand-item italic">Feed&Food</span>
        <span class="brand-item">LA <span class="text-sm">COACH BASE</span></span>
        <span class="brand-item">Bridgette</span>
        <span class="brand-item">amazero</span>
        <span class="brand-item italic">Vibes</span>
      </div>
    </div>
  </section>
</template>

<script setup>
// لا يوجد سكريبت مطلوب هنا لأن المكون بسيط
</script>

<style scoped>
.bg-darkBlue {
  background-color: #0a192f;
}

.grid-cols-auto-fit {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  justify-items: center;
}

.brand-item {
  color: white;
  font-size: 1.25rem;
  font-weight: bold;
  transition: opacity 0.3s ease-in-out;
}

.brand-item:hover {
  opacity: 0.8;
}

@media (max-width: 640px) {
  .brand-item {
    font-size: 1rem;
  }
}
</style>
