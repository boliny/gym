<template>
  <div class="bg-gradient-to-r from-indigo-900 to-purple-500 min-h-screen flex items-center justify-center p-4 sm:p-6">
    <div class="flex flex-col-reverse md:flex-row items-center max-w-5xl w-full bg-white shadow-2xl rounded-lg overflow-hidden">
      
      <!-- القسم الأيمن - محتوى نصي -->
      <div class="w-full md:w-1/2 p-6 sm:p-8 md:p-10 text-white text-left bg-gradient-to-r from-purple-700 to-purple-500">
        <span class="text-yellow-300 font-semibold text-sm block">Get Instant Access to The Free</span>
        <h2 class="text-2xl sm:text-3xl md:text-4xl font-bold mt-2 leading-snug">
          SELF DEVELOPMENT COURSE
        </h2>
        <p class="mt-4 text-sm sm:text-base leading-relaxed">
          Learn about self-development and unlock your full potential. Take the first step toward personal growth today!
        </p>
        <button class="mt-6 bg-yellow-400 text-black font-bold py-3 px-6 rounded-lg shadow-lg hover:bg-yellow-500 transition duration-300 w-full sm:w-auto">
          START FOR FREE
        </button>
      </div>

      <!-- القسم الأيسر - فيديو يوتيوب -->
      <div class="w-full md:w-1/2 relative">
        <div class="aspect-w-16 aspect-h-9">
          <iframe
            class="w-full h-full rounded-t-lg md:rounded-none"
            src="https://www.youtube.com/embed/6dNryy5V7jM"
            frameborder="0"
            allowfullscreen>
          </iframe>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: "SelfDevelopmentSection",
};
</script>

<style scoped>
/* تحسين توافق الفيديو للأجهزة الصغيرة */
.aspect-w-16 {
  position: relative;
  width: 100%;
}

.aspect-h-9::before {
  content: "";
  display: block;
  padding-top: 56.25%; /* نسبة العرض إلى الارتفاع للفيديو */
}

.aspect-h-9 iframe {
  position: absolute;
  width: 100%;
  height: 100%;
}
</style>
