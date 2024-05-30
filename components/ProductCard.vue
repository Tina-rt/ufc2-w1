<template>
  <div class="product-card">
    <img :src="props.image" alt="">
    <div class="product-info py-5 flex justify-between items-center">
      <div>
        <h1 class="text-2xl ">{{ props.title }}</h1>
        <p class="">{{ props.description }}</p>
      </div>
      <div class="next">
        <ChevronRightIcon class="cursor-pointer w-12 h-12 bg-[#FBE8FE] p-2 rounded-full" />
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>

import { ChevronRightIcon } from '@heroicons/vue/16/solid';

const props = defineProps({
  title: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
  image: {
    type: String,
    required: true,
  },
});
</script>

<style lang="scss" scoped>
.product-card {
  width: 100%;
  max-width: 500px;
  aspect-ratio: 5/4;

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-top-right-radius: 20%;
  }
}
</style>

