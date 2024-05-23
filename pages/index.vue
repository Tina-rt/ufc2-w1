<template>
    <div class="main relative">
        <Navbar class="fixed top-3 left-0" />
        <div class="hero screen py-24  flex flex-col w-full items-center relative">
            <div class="circle green" v-for="i in Array.from({ length: 3 }, (v, k) => k)" :style="{
                bottom: `${i * 40}px`,
                right: `${i * 300 + 30}px`
            }">

            </div>
            <div class="flex justify-between z-10 px-20">
                <div class="hero-content w-2/5 flex flex-col gap-5 justify-evenly h-full">
                    <div class="hero-title ">
                        <h1 class=" font-bold">
                            The Best View In The World From Your Site
                        </h1>
                    </div>
                    <div class="hero-description">
                        <p>
                            Provides you with the latest online learning system
                            and material that helps your knowledge growing
                        </p>
                    </div>
                    <div class="hero-button flex items-center gap-4">
                        <Button text="Get Started" severity="primary" />
                        <div class="btn-watch-video flex justify-between items-center gap-2">
                            <PlayIcon class="h-6 w-6 text-black bg-white rounded-full p-1" />
                            <span class="underline">Watch Video</span>
                        </div>
                    </div>
                </div>
                <div class="hero-image w-2/4">
                    <img src="~/assets/img/hero.webp" alt="hero image" />
                </div>
            </div>
            <div class="brand-section z-10 flex items-center w-full justify-evenly py-20">
                <div class="brand w-20" v-for="brand in brands">
                    <img class="w-full" :src="`images/${brand}`"
                        alt="netflix" />
                </div>
            </div>


            <!-- <div class="circle blue"></div>
            <div class="circle blue"></div>
            <div class="circle"></div> -->
        </div>
        <HowItWorks />
    </div>
</template>

<script lang="ts" setup>
import { PlayIcon } from "@heroicons/vue/16/solid";

const brands = ref([
    "classic.webp",
    "brand.webp",
    "modernhome.webp",
    "nature_home.webp",
    "vs.webp"
])

</script>

<style lang="scss" scoped>
.hero {
    height: 100vh;
    color: white;
    position: relative;
    background-color: #BF8BE8;
    background: linear-gradient(180deg, #BF8BE8 0%, #ffffff 100%);

    .hero-title{
        h1{
            font-size: 5rem;
        }
    }

}

.circle.green {
    background-color: #F4D7AA;

}

.circle {
    width: 40rem;
    height: 40rem;
    border-radius: 50%;
    position: absolute;
    z-index: 1;
    filter: blur(40px);
}

.screen {
    padding-inline: 5rem;
}

.brand-section{
    border-top: 1px solid rgba(0, 0, 0, 0.112);
    border-bottom: 1px solid rgba(0, 0, 0, 0.112);
    margin-top: 20px;
}
</style>
