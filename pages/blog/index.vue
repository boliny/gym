<template>
  <div class="container mx-auto px-4">
    <!-- Header -->
    <header class="text-center py-8">
      <h1 class="text-4xl font-bold">BLOG</h1>
    </header>
    
    <!-- Main Content -->
    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
      <!-- Main Post -->
      <div class="md:col-span-2">
        <div class="relative">
          <img 
            src="https://themes.pixelwars.org/efor/demo-04/wp-content/uploads/sites/6/2018/09/011-550x362.jpg" 
            alt="Main Post Image" 
            class="w-full h-[400px] object-cover rounded-lg"
          />
        </div>
        <h2 class="text-2xl font-bold mt-4">STOP IGNORING THESE 7 INSPIRING TRUTHS</h2>
      </div>
      
      <!-- Sidebar -->
      <aside>
        <div class="mb-4">
          <input 
            type="text" 
            placeholder="Search ..." 
            class="w-full px-4 py-2 border rounded-full"
          />
        </div>
        <h3 class="text-xl font-bold mb-2">MUST READ</h3>
        <div class="space-y-4">
          <div class="flex items-center space-x-4">
            <img src="https://themes.pixelwars.org/efor/demo-04/wp-content/uploads/sites/6/2018/09/011-550x362.jpg" alt="Post" class="w-16 h-16 object-cover rounded-lg" />
            <p class="text-sm">STOP IGNORING THESE 7 INSPIRING TRUTHS</p>
          </div>
          <div class="flex items-center space-x-4">
            <img src="https://themes.pixelwars.org/efor/demo-04/wp-content/uploads/sites/6/2018/09/011-550x362.jpg" alt="Post" class="w-16 h-16 object-cover rounded-lg" />
            <p class="text-sm">HOW TO BE 1% BETTER EVERY DAY</p>
          </div>
          <div class="flex items-center space-x-4">
            <img src="https://themes.pixelwars.org/efor/demo-04/wp-content/uploads/sites/6/2018/09/011-550x362.jpg" alt="Post" class="w-16 h-16 object-cover rounded-lg" />
            <p class="text-sm">HOW TO BECOME RIDICULOUSLY SELF-AWARE IN 20 MINUTES</p>
          </div>
        </div>
      </aside>
    </div>
    <!-- Blog Post -->
  <div class="max-w-2xl mx-auto text-center">
    <p class="text-sm uppercase tracking-wide text-gray-500">Life</p>
    <h1 class="text-3xl font-bold mt-2">STOP IGNORING THESE 7 INSPIRING TRUTHS</h1>
    
    <div class="flex justify-center items-center space-x-4 text-gray-500 text-sm mt-2">
      <span>OCTOBER 14, 2018</span>
      <span class="flex items-center space-x-1"><i class="fas fa-share"></i> <span>SHARE</span></span>
      <span class="flex items-center space-x-1"><i class="fas fa-heart"></i> <span>5</span></span>
      <span class="flex items-center space-x-1"><i class="fas fa-eye"></i> <span>713 VIEWS</span></span>
    </div>
    
    <p class="text-gray-700 mt-4 leading-relaxed">
      People know who they have the potential to be. The challenge is seeing that process through. Self-development is an art. It takes time. It requires patience. It asks you to step outside your comfort zone. It...
    </p>
    
    <button class="mt-6 px-6 py-2 border border-black rounded-full text-black hover:bg-black hover:text-white transition-all">
      READ MORE
    </button>
  </div>
  <div class="container mx-auto px-4 py-8 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
    <!-- Blog Posts -->
    <div v-for="(post, index) in posts" :key="index" class="max-w-md mx-auto text-center">
      <img :src="post.image" alt="Post Image" class="w-full h-48 object-cover rounded-lg">
      <p class="text-sm uppercase tracking-wide text-gray-500 mt-2">{{ post.category }}</p>
      <h1 class="text-2xl font-bold mt-2">{{ post.title }}</h1>
      
      <div class="flex justify-center items-center space-x-4 text-gray-500 text-sm mt-2">
        <span>{{ post.date }}</span>
        <span class="flex items-center space-x-1"><i class="fas fa-share"></i> <span>SHARE</span></span>
        <span class="flex items-center space-x-1"><i class="fas fa-heart"></i> <span>{{ post.likes }}</span></span>
        <span class="flex items-center space-x-1"><i class="fas fa-eye"></i> <span>{{ post.views }} VIEWS</span></span>
      </div>
      
      <p class="text-gray-700 mt-4 leading-relaxed">
        {{ post.description }}
      </p>
      
      <button class="mt-6 px-6 py-2 border border-black rounded-full text-black hover:bg-black hover:text-white transition-all">
        READ MORE
      </button>
    </div>
  </div>
  </div>
</template>

<style>
.container {
  max-width: 1024px;
}
</style>


<script>
export default {
  data() {
    return {
      posts: [
        {
          category: "Life",
          title: "STOP IGNORING THESE 7 INSPIRING TRUTHS",
          date: "OCTOBER 14, 2018",
          likes: 5,
          views: 713,
          description: "People know who they have the potential to be. The challenge is seeing that process through...",
          image: "https://themes.pixelwars.org/efor/demo-04/wp-content/uploads/sites/6/2018/09/010-550x362.jpg"
        },
        {
          category: "Improve",
          title: "HOW TO BE 1% BETTER EVERY DAY",
          date: "OCTOBER 14, 2018",
          likes: 3,
          views: 429,
          description: "Compounding is the greatest mathematical discovery of all time. The quest to become a better version...",
          image: "https://themes.pixelwars.org/efor/demo-04/wp-content/uploads/sites/6/2018/09/010-550x362.jpg"
        },
        {
          category: "Life",
          title: "HOW TO BECOME RIDICULOUSLY SELF-AWARE IN 20 MINUTES",
          date: "OCTOBER 13, 2018",
          likes: 1,
          views: 253,
          description: "Four years ago my sister got me something that would dramatically alter the direction of my life...",
          image: "https://themes.pixelwars.org/efor/demo-04/wp-content/uploads/sites/6/2018/09/010-550x362.jpg"
        },
        {
          category: "Success",
          title: "THE KEY HABITS OF HIGHLY SUCCESSFUL PEOPLE",
          date: "OCTOBER 12, 2018",
          likes: 8,
          views: 1023,
          description: "Success leaves clues. The most successful people have common habits that contribute to their growth...",
          image: "https://themes.pixelwars.org/efor/demo-04/wp-content/uploads/sites/6/2018/09/010-550x362.jpg"
        },
        {
          category: "Mindset",
          title: "TRAIN YOUR BRAIN TO THINK POSITIVELY",
          date: "OCTOBER 11, 2018",
          likes: 4,
          views: 876,
          description: "Your thoughts shape your reality. Training your brain to think positively can change your life...",
          image: "https://themes.pixelwars.org/efor/demo-04/wp-content/uploads/sites/6/2018/09/010-550x362.jpg"
        }
      ]
    };
  }
};
</script>
