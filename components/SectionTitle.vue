<template>
  <div class="title text-center p-5">
    <h2 class="text-4xl">{{ props.title }}</h2>
    <p class="">{{ props.subtitle }}</p>
  </div>
</template>

<script lang="ts" setup>
const props = defineProps<{
	title: string;
	subtitle: string;
}>();
</script>

<style></style>