<template>
    <div class="main relative flex flex-col">
        <Navbar class=" navbar" />
        <div class="hero screen py-24  flex flex-col w-full items-center relative ">
            <CircleAnimated />
            <CircleAnimated />
            <div class="flex flex-col justify-between md:items-center lg:items-center z-10 px-0 lg:px-0 md:px-0 w-full flex-wrap md:flex-row sm:flex-col">
                <div class="hero-content lg:w-2/5 md:w-2/5 w-full flex flex-col gap-5 justify-evenly h-full ">
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
                <div class="hero-image md:w-2/4 w-full">
                    <img src="~/assets/img/hero.webp" alt="hero image" />
                </div>
            </div>
            <div class="brand-section z-10 flex items-center w-full justify-evenly py-20 flex-wrap gap-4">
                <div class="brand w-20" v-for="brand in brands">
                    <img class="w-full" :src="`images/${brand}`"
                        alt="netflix" />
                </div>
            </div>


            <!-- <div class="circle blue"></div>
            <div class="circle blue"></div>
            <div class="circle"></div> -->
        </div>
        <div class="lg:px-20 md:px-16 px-10">
            <HowItWorks id="howitworks"/>
            <Features />
            <OurProducts id="products"/>
        </div>
        <Testimonials />
        <BlogAndNews id="blog" />
        <Footer id="contact" />
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

.navbar{
    position: fixed;
    top: 0;
    left: 0;
    z-index: 99;

    @media (max-width: 768px) {
        right: 0;
        left: 0;
        max-width: 100dvw;
    }
}
.hero {
    color: white;
    position: relative;
    background-color: #BF8BE8;
    background: linear-gradient(180deg, #BF8BE8 0%, #ffffff 100%);

    .hero-title{
        h1{
            font-size: 3.3rem;
            text-align: left;
            word-spacing: 0.5rem;
        }
    }
    .hero-description p{
        color: white !important;
    }

}



.screen {
    padding-inline: 5rem;
    @media screen and (max-width: 1000px) {
        padding-inline: 2rem;
    }
}

.brand-section{
    border-top: 1px solid rgba(0, 0, 0, 0.112);
    border-bottom: 1px solid rgba(0, 0, 0, 0.112);
    margin-top: 20px;
}
</style>
