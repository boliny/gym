<template>
  <div class="bg-gradient-to-r from-indigo-900 to-purple-500 min-h-screen flex items-center justify-center p-6">
    <div class="flex flex-col md:flex-row items-center max-w-6xl w-full bg-white shadow-2xl rounded-lg overflow-hidden">
      <!-- القسم الأيسر - فيديو يوتيوب -->
      <div class="w-full md:w-1/2">
        <iframe class="w-full h-64 md:h-full" src="https://www.youtube.com/embed/6dNryy5V7jM" frameborder="0" allowfullscreen></iframe>
      </div>
      
      <!-- القسم الأيمن - محتوى نصي -->
      <div class="w-full md:w-1/2 p-10 text-white text-left bg-gradient-to-r from-purple-700 to-purple-500">
        <span class="text-yellow-300 font-semibold text-sm">Get Instant Access to The Free</span>
        <h2 class="text-4xl font-bold mt-2">SELF DEVELOPMENT COURSE</h2>
        <p class="mt-4 text-lg">Learn about how them you went down prying the wedding ring off his cold, dead finger. I don't know what you did, Fry, but once again, you screwed up! Now all the planets are gonna start cracking wise about our mamas.</p>
        <button class="mt-6 bg-yellow-400 text-black font-bold py-3 px-6 rounded-lg shadow-lg hover:bg-yellow-500 transition duration-300">START FOR FREE</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SelfDevelopmentSection",
};
</script>

<style>
</style>
