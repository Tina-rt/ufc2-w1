<template>
  <div class="testimonial-card flex flex-col md:flex-row lg:flex-row justify-center items-center gap-4 w-full">
    <div class="testimonial-image lg:w-1/2 md:w-1/2 w-full">
      <img :src="props.testimonial.image" alt="testimonial" />
    </div>
    <div class="testimonial-content lg:w-1/2 md:w-1/2 w-full">
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
  // height: 400px;
  aspect-ratio: 7/4;

  @media screen and (max-width: 1000px) {
    min-width: 100%;
    
  }
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

