<template>
  <div class="video-section">
      <div class="rec rec1"></div>
      <div class="rec rec2"></div>
      <div class="play-btn">
          <PlayIcon class="h-12 w-12 bg-white rounded-full p-2" />
      </div>
      <div class="image">
          <img :src=props.image alt="Video Thumb">
      </div>
  </div>
</template>

<script lang="ts" setup>
import { PlayIcon } from '@heroicons/vue/16/solid';

const props = defineProps({
  image: {
    type: String,
    required: true,
  },
});
</script>

<style scoped lang="scss">
.video-section {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  max-width: 600px;
  .rec {
      width: 100px;
      height: 100px;
      background-color: #C507ED;
      border-radius: 20px;
      position: absolute;
      transform: scale(1.3);
      box-shadow: 2px 5px 10px 0px rgba(90, 90, 90, 0.5);
      z-index: -1;
  }

  .rec1 {
      top: 5px;
      left: 5px;
  }

  .rec2 {
      bottom: 5px;
      right: 5px;
  }

  .play-btn {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      z-index: 2;
      color: #C507ED;
  }

  .image {
      width: 100%;
      height: 100%;
      object-fit: cover;
      border-radius: 20px;

      img {
          width: 100%;
          height: 100%;
          object-fit: cover;
          border-radius: 30px;
      }
  }
}
</style>