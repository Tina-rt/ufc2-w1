<template>
  <div>
    <div class="w-full ">
      <div class="header text-center w-full">
        <h1 class="text-4xl ">Our Products</h1>
        <p class="">Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque, quisquam.</p>

      </div>
      <div class="product-grid w-full place-items-center grid grid-cols-2 justify-center my-20 px-20 gap-16 " >
        <ProductCard v-for="product in products" :key="product.title" :image="product.image" :title="product.title" :description="product.description" />
      </div>
    </div>

  </div>
</template>

<script lang="ts" setup>
const products = [
  {
    image: 'https://www.newsshooter.com/wp-content/uploads/2016/10/DSC05740-1-1.jpg',
    title: 'DJI Mavic 2 Pro',
    description: 'Know for its excellent camera quality',
  },
  {
    image: 'https://assets.newatlas.com/dims4/default/e8190e4/2147483647/strip/true/crop/1575x957+0+0/resize/1575x957!/quality/90/?url=http%3A%2F%2Fnewatlas-brightspot.s3.amazonaws.com%2Farchive%2Fdji-phantom4-pro-upgrade-4.png',
    title: 'DJI Phantom 4 Pro',
    description: 'Powerful camera with a 1-inch CMOS',
  },
  {
    image: 'https://www.cnet.com/a/img/resize/ab1e27d7536a5cd2de7e0dbb3c0da6b78eb5a82c/hub/2020/11/04/27c1c2b3-494e-4776-981c-a5936e004dcb/dji-mini-2-06.jpg?auto=webp&fit=crop&height=1200&width=1200',
    title: 'DJI Mini 2',
    description: 'Popular for its ease of use and portability',
  },
  {
    image: 'https://i.pcmag.com/imagery/reviews/05dazeoMotZdEE4PMn3uNey-10.fit_scale.size_760x427.v1569479883.jpg',
    title: 'Yuneec Typhoon',
    description: '360-degree camera with a 12.3-inch screen',
  },
];
</script>

<style></style>