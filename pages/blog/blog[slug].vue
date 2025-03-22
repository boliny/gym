<template>
  <div class="container">
    <h1 class="title">{{ blog.title }}</h1>
    <img :src="blog.image" alt="Blog image" class="blog-img" />
    <p class="blog-content">{{ blog.content }}</p>
  </div>
</template>

<script setup>
const route = useRoute();
const { data: blog } = await useAsyncData(`blog-${route.params.slug}`, () =>
  fetch(`/api/blogs/${route.params.slug}`).then((res) => res.json())
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
.blog-img {
  width: 100%;
  border-radius: 8px;
  margin-bottom: 20px;
}
.blog-content {
  font-size: 16px;
  line-height: 1.6;
}
</style>
