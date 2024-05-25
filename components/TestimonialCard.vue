<template>
  <div class="testimonial-card flex justify-center items-center gap-4 w-full">
    <div class="testimonial-image w-1/2">
      <img :src="props.testimonial.image" alt="testimonial" />
    </div>
    <div class="testimonial-content w-1/2 ">
      <p class="text-quotes py-4 text-black">
        "{{ props.testimonial.quote }}"
      </p>
      <p class="text-authors text-black">{{ props.testimonial.author }}</p>
      <p class="text-authors-function text-sm text-black">{{ props.testimonial.authorFunction }}</p>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { type Testimonial } from '~/models/Testimonial';
const props = defineProps<{
  testimonial: Testimonial;
}>();
</script>

<style scoped lang="scss">
.testimonial-card {
  background-color: #FEF6FF;
  padding:  30px;
  border-radius: 20px;
  min-width: 700px;
  height: 400px;
} 
.testimonial-image {
  // width: 100%;
  height: 100%;
  img{
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 20px;
  }
}

.text-authors{
  font-weight: 600;
  font-size: 1.2rem;
}
</style>

