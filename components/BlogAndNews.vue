<template>
  <div>
    <SectionTitle title="Blog & News" subtitle="Stay Updated with Our Latest Articles" />
    <div class="blog-card-list grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 place-items-center gap-4 lg:px-40 md:px-20 px-5 py-5">
      <BlogCard v-for="blog in blogList" :key="blog.title" :title="blog.title" :description="blog.description" :author="blog.author" :category="blog.category" :date="blog.date" :image="blog.image" />
    </div>
  </div>
</template>

<script lang="ts" setup>
const blogList = ref([
  {
    title: "FAA Announces New Drones Rules to Increase Safety and Regulation",
    description: "The Federal Aviation Administration (FAA) implemented new regulation",
    author: "By Admin",
    category: "Developing",
    date: "August 5, 2023",
    image: "https://picsum.photos/300/300",
  },
  {
    title: "FAA Announces New Drones Rules to Increase Safety and Regulation",
    description: "The Federal Aviation Administration (FAA) implemented new regulation",
    author: "By Admin",
    category: "Developing",
    date: "August 5, 2023",
    image: "https://picsum.photos/200/300",
  },
]);
</script>

<style>

</style>