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
        <div class="relative overflow-hidden rounded-lg cursor-pointer transition-transform transform hover:scale-105 hover:shadow-lg">
          <img 
            src="https://themes.pixelwars.org/efor/demo-04/wp-content/uploads/sites/6/2018/09/011-550x362.jpg" 
            alt="Main Post Image" 
            class="w-full h-[400px] object-cover"
          />
        </div>
        <h2 class="text-2xl font-bold mt-4 cursor-pointer hover:text-blue-600 transition-colors">
          STOP IGNORING THESE 7 INSPIRING TRUTHS
        </h2>
        <div class="flex items-center space-x-4 text-sm text-gray-500 mt-2">
          <span><i class="fas fa-calendar-alt mr-1"></i> Apr 8, 2025</span>
          <span><i class="fas fa-eye mr-1"></i> 980</span>
          <span class="flex items-center space-x-1 cursor-pointer">
            <i class="fas fa-heart text-red-500"></i><span>245</span>
          </span>
          <span><i class="fas fa-share-alt mr-1"></i> Share</span>
        </div>
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
          <div class="flex items-center space-x-4 cursor-pointer hover:bg-gray-100 p-2 rounded-lg transition">
            <img src="https://themes.pixelwars.org/efor/demo-04/wp-content/uploads/sites/6/2018/09/011-550x362.jpg" alt="Post" class="w-16 h-16 object-cover rounded-lg" />
            <p class="text-sm">STOP IGNORING THESE 7 INSPIRING TRUTHS</p>
          </div>
          <div class="flex items-center space-x-4 cursor-pointer hover:bg-gray-100 p-2 rounded-lg transition">
            <img src="https://themes.pixelwars.org/efor/demo-04/wp-content/uploads/sites/6/2018/09/011-550x362.jpg" alt="Post" class="w-16 h-16 object-cover rounded-lg" />
            <p class="text-sm">HOW TO BE 1% BETTER EVERY DAY</p>
          </div>
          <div class="flex items-center space-x-4 cursor-pointer hover:bg-gray-100 p-2 rounded-lg transition">
            <img src="https://themes.pixelwars.org/efor/demo-04/wp-content/uploads/sites/6/2018/09/011-550x362.jpg" alt="Post" class="w-16 h-16 object-cover rounded-lg" />
            <p class="text-sm">HOW TO BECOME RIDICULOUSLY SELF-AWARE IN 20 MINUTES</p>
          </div>
        </div>
      </aside>
    </div>

    <!-- Blog Highlight -->
    <div class="max-w-2xl mx-auto text-center mt-10">
      <p class="text-sm uppercase tracking-wide text-gray-500">Life</p>
      <h1 class="text-3xl font-bold mt-2 cursor-pointer hover:text-blue-600 transition">
        STOP IGNORING THESE 7 INSPIRING TRUTHS
      </h1>
      <p class="text-gray-700 mt-4 leading-relaxed">
        People know who they have the potential to be. The challenge is seeing that process through. Self-development is an art. It takes time. It requires patience. It asks you to step outside your comfort zone. It...
      </p>
      <button class="cursor-pointer mt-6 px-6 py-2 border border-black rounded-full text-black hover:bg-black hover:text-white transition-all">
        READ MORE
      </button>
    </div>

    <!-- Blog Posts -->
    <div class="container mx-auto px-4 py-8 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      <div v-for="(post, index) in posts" :key="post.id" class="max-w-md mx-auto text-center">
        <div
          class="overflow-hidden transition delay-150 cursor-pointer"
        >
        <div  @click="goToItem(post.id)"  class="relative overflow-hidden rounded-lg cursor-pointer group">
          <!-- الصورة -->
          <img
         
            :src="post.thumbnail"
            alt="Post Image"
            class="w-full h-48 object-cover transition-transform duration-500 delay-150 group-hover:scale-105"
          />
          
          <!-- الـ Overlay -->
          <div class="absolute inset-0 bg-black/10 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
        </div>
        
          
        </div>
        <p class="text-sm uppercase tracking-wide text-gray-500 mt-2">
          {{ post.category }}
        </p>
        <h1 @click="goToItem(post.id)"
          class="text-2xl font-bold mt-2 cursor-pointer hover:text-blue-600 transition-colors"
        >
          {{ post.title }}
        </h1>
        <div class="flex justify-center items-center space-x-4 text-sm text-gray-500 mt-2">
          <span><i class="fas fa-calendar-alt mr-1"></i> Apr 8, 2025</span>
          <span><i class="fas fa-eye mr-1"></i> {{ post.views }}</span>
          <span
          class="flex items-center space-x-1 cursor-pointer"
          @click="toggleLike(post.id)"
        >
          <i
            class="fas fa-heart transition-colors duration-300"
            :class="likedPosts.includes(post.id) ? 'text-red-500' : 'text-gray-400'"
          ></i>
          <span>{{ post.likes }}</span>
        </span>
        

          <span><i class="fas fa-share-alt mr-1"></i> Share</span>
        </div>

        <p class="text-gray-700 mt-4 leading-relaxed">
          {{ post.description }}
        </p>
        <button @click="goToItem(post.id)" class="cursor-pointer mt-6 px-6 py-2 border border-black rounded-full text-black hover:bg-black hover:text-white transition-all">
          READ MORE
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const { data } = await useFetch("https://dummyjson.com/products");
const posts = ref([]);
const likedPosts = ref([]);

onMounted(() => {
  posts.value = data.value.products.map((post) => ({
    ...post,
    views: getRandomViews(),
    likes: getRandomLikes()
  }));
});

const getRandomViews = () => Math.floor(Math.random() * 1000 + 100);
const getRandomLikes = () => Math.floor(Math.random() * 300 + 20);

const toggleLike = (postId) => {
  const index = posts.value.findIndex((p) => p.id === postId);
  if (likedPosts.value.includes(postId)) {
    // شيل اللايك
    posts.value[index].likes--;
    likedPosts.value = likedPosts.value.filter((id) => id !== postId);
  } else {
    // ضيف لايك
    posts.value[index].likes++;
    likedPosts.value.push(postId);
  }
};

const goToItem = (id) => {
  navigateTo(`/blog/${id}`);
};


</script>

<style>
.container {
  max-width: 1024px;
}
</style>

