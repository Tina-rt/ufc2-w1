<template>
  <div class="card flex flex-col gap-2">
    <div class="image">
      <img :src="props.image" alt="" />
    </div>
    <p class="author-category-date">{{ props.author }} - {{ props.category }} - {{ props.date }}</p>
    <h3 class="text-xl">{{ props.title }}</h3>
    <p class="">{{ props.description }}</p>
    <div class="flex items-center justify-between py-5">
      <div class="view-post flex items-center gap-2 text-blue-500 hover:underline underline-offset-8 cursor-pointer"><span >View Post</span> <ArrowUpRightIcon class="w-6 h-6 text-blue-500" /></div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ArrowUpRightIcon } from "@heroicons/vue/24/outline";
const props = defineProps<{
	image: string;
	title: string;
	description: string;
	author: string;
	category: string;
	date: string;
}>();
</script>

<style scoped lang="scss">
.card{
  width: 100%;
  max-width: 500px;
}
.card .image{
  width: 100%;
  height: 300px;
  border-radius: 20px;
  img{
    width: 100%;
    height: 100%;
    border-radius: 20px;
    object-fit: cover;
  }
}
</style>

