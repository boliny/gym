<template>
  <div class="container">
    <h1 class="title">المدونة</h1>
    <div class="grid">
      <BlogCard v-for="blog in blogs" :key="blog.slug" :blog="blog" />
    </div>
  </div>
</template>

<script setup>
const { data: blogs } = await useAsyncData("blogs", () =>
  fetch("/api/blogs").then((res) => res.json())
);
</script>

<style scoped>
.container {
  max-width: 800px;
  margin: auto;
  padding: 20px;
}
.title {
  text-align: center;
  margin-bottom: 20px;
}
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
}
</style>
