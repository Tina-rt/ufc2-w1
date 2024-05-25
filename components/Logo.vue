<template>
  <div class="flex flex-col items-center gap-2 w-[30px] h-[30px]" >
    <img src="~/assets/img/logo.png" class="brand" alt="logo" />
    <span class="font-bold" :style="{ filter: props.invert ? 'invert(1)' : 'invert(0)' }">DRONE</span>
  </div>
</template>

<script lang="ts" setup>
const props = defineProps<{
  invert?: boolean
}>()
</script>

<style>

</style>