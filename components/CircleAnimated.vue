<template>
  <div class="w-full overflow-hidden">
    <div class="circle green" :style="{
      bottom: `${x}px`,
      right: `${y}px`,
      width: `${width}rem`,
    }">
    </div>

  </div>
</template>

<script lang="ts" setup>

const x = ref(0);
const y = ref(0);
const width = ref(10);
const height = ref(10);
width.value = Math.random() * (40 - 10) + 10;
height.value = Math.random() * (40 - 10) + 10;

const lauch = () => {
  x.value = Math.random() * (window.innerWidth - width.value) - width.value;
  y.value = Math.random() * (window.innerHeight - height.value) - height.value;
}

onNuxtReady(() => {
  lauch()
  setInterval(() => {
    lauch()
  }, 10000);
})
</script>

<style scoped>
.circle.green {
  background-color: #F4D7AA;

}

.circle {

  border-radius: 50%;
  position: absolute;
  aspect-ratio: 1/1;
  z-index: 1;
  filter: blur(40px);
  transition: all 8s ease;
}
</style>

