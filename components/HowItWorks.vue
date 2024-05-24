<template>
  <div class="w-full flex flex-col items-center justify-start py-10">
    <div class="title flex flex-col gap-10 items-center">
      <h1 class="text-5xl">How It Works</h1>
      <p class=" text-gray-500 w-2/3 text-center">Our drones capture moments with a bird's eye view</p>
    </div>
    <div class="feature-list w-full px-28 my-10 py-10 flex justify-center gap-20 ">
      <div class="feature flex flex-col items-center gap-8 min-w-48" v-for="f in feature">
        <div class="feature-image w-20">
          <img :src="f.image" alt="feature image">
        </div>
        <div class="feature-title">
          <h1 class="text-4xl">{{ f.title }}</h1>
        </div>
        <div class="feature-description text-center text-gray-500">
          <p>{{ f.description }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
const feature = ref([
  {
    image: "https://img.freepik.com/vecteurs-premium/icone-drone-icone-quadricoptere-illustration-vectorielle_756957-1039.jpg",
    title: "Propellers",
    description: "Generate thrust to lift the drone off the ground and control its movement in different directions."
  },
  {
    image: "https://img.freepik.com/premium-photo/3d-map-pointer-location-map-icon-white-texture-white-location-pin-navigation-web-location-poi_651618-814.jpg",
    title: "GPS",
    description: "GPS allows the drone to follow pre-programmed flight path or waypoints autonomously"
  },
  {
    image: "https://img.freepik.com/vecteurs-premium/icone-drone-icone-quadricoptere-illustration-vectorielle_756957-1039.jpg",
    title: "Gyroscope",
    description: "The gyroscope measures the drone's angular rate or rotational movement around its axes."
  },
])
</script>

<style></style>