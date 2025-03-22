<template>
  <div class="card">
    <img :src="blog.image" alt="Blog image" class="card-img" />
    <h2 class="card-title">{{ blog.title }}</h2>
    <p class="card-desc">{{ blog.description }}</p>
    <NuxtLink :to="`/blog/${blog.slug}`" class="read-more">اقرأ المزيد</NuxtLink>
  </div>
</template>

<script setup>
defineProps(["blog"]);
</script>

<style scoped>
.card {
  border: 1px solid #ddd;
  padding: 15px;
  border-radius: 8px;
  background: white;
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
}
.card-img {
  width: 100%;
  border-radius: 5px;
}
.card-title {
  font-size: 18px;
  margin: 10px 0;
}
.card-desc {
  font-size: 14px;
  color: #666;
}
.read-more {
  display: block;
  margin-top: 10px;
  color: blue;
}
</style>
