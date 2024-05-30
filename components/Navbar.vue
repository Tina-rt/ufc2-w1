<template>
    <div ref="navbar" class="navbar text-white px-5 lg:px-20 md:px-15  relative gap-5 lg:gap-0 md:gap-0">
        <div class="navbar-item  flex-col flex justify-start items-start flex-grow "
            :class="{ 'filter-inverse': isScrolled }">
            <Logo />
        </div>
        <div class="navbar-item nav-items md:justify-center lg:justify-center justify-start md:items-center lg:items-center items-end "
            :class="{ 'filter-inverse': isScrolled, 'showNavItem': navIsOpen }">

            <div class="nav-item"><a href="#howitworks">How it works</a></div>
            <div class="nav-item"><a href="#services">Services</a></div>
            <div class="nav-item"><a href="#features">Features</a></div>
            <div class="nav-item"><a href="#products">Products</a></div>
            <div class="nav-item"><a href="#contact">Contact us</a></div>

        </div>
        <div class="navbar-item button-group hidden lg:flex md:flex items-center flex-grow justify-end">
            <Button text="Login" severity="primary" />
            <Button text="Register" severity="secondary" />
        </div>
        <div @click="toggleNav" class="block lg:hidden md:hidden hamburger text-3xl mt-5"
            :class="{ 'filter-inverse': isScrolled }">
            <i class="pi pi-chevron-down transition-all duration-700" :class="{ 'rotate-180': navIsOpen }"></i>
        </div>

    </div>
</template>

<script lang="ts" setup>
import { ref, onMounted, onUnmounted } from 'vue';

const navbar = ref<HTMLDivElement>();

const isScrolled = ref(false);

const handleScroll = () => {
    const scrollPosition = window.scrollY;
    isScrolled.value = scrollPosition > window.innerHeight; // 100vh
};

const navIsOpen = ref(false);
const isMobile = computed(() => {
    return window.innerWidth < 800
});
const toggleNav = () => {
    if (navbar.value) {
        navbar.value.classList.toggle('showNav');
        // navbar.value.style.maxHeight = navIsOpen.value ? '100px' : '80dvh';
        // navbar.value.style.height = navIsOpen.value ? '100px' : '80dvh';
        navIsOpen.value = !navIsOpen.value;
    }
}

onMounted(() => {
    window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll);
});

</script>

<style scoped lang="scss">
.navbar {
    display: grid;
    width: 100%;
    grid-template-columns: 1fr 3fr 1fr;
    // z-index: 0;
    // background: linear-gradient(to bottom, rgba(255, 255, 255, 0.342), rgba(255, 255, 255, 0.247));
    backdrop-filter: blur(30px);
    mask-image: linear-gradient(180deg, rgba(255, 255, 255, 1) 0%, rgba(255, 255, 255, 0.6054796918767507) 86%, rgba(255, 255, 255, 0) 100%);
    transition: all 0.5s ease;
    max-height: 80dvh;
    height: 100px;
    align-items: center;
    

    @media screen and (max-width: 1000px) {
        grid-template-columns: 1fr 3fr 2fr;
    }

    @media screen and (max-width: 768px) {
        display: flex;
        justify-content: space-between;
        align-items: start;
        // height: auto;
        max-height: 100px;
        // height: 100px;
        padding: 20px;

        max-width: 100dvw;
        mask-image: linear-gradient(180deg, rgba(255, 255, 255, 1) 0%, rgba(255, 255, 255, 0.76) 98%, rgba(255, 255, 255, 0.382) 100%);
        overflow: hidden;
        // overflow-y: scroll;
        // overflow-x: hidden;
    }
}

.showNav {
    align-items: start;
    height: 80dvh;
    max-height: 80dvh;
}

.showNavItem{
    opacity: 1 !important;
}

.navbar:hover {
    backdrop-filter: blur(20px);
    cursor: pointer;
}

.navbar-item {
    transition: all 0.5s ease;

}

.nav-item {
    transition: all 0.3s ease;
    min-width: fit-content;
}

.nav-items {
    display: flex;
    gap: 40px;
    font-size: 1.2rem;
    font-weight: 300;
    min-width: fit-content;
    align-items: center;
    flex-wrap: wrap;
    @media screen and (max-width: 768px) {
        margin-top: 20px;
        opacity: 0.4;
    }
    @media (max-width: 768px) {
        // display: none;
        flex-direction: column;
        min-height: 100px;
        // min-width: 100%;
        overflow-y: scroll;
    }
}

.button-group {
    // display: flex;
    flex-direction: row;
    gap: 10px;
    min-width: fit-content;
}

.navbar .brand {
    width: 50px;
    height: 50px;
}

.filter-inverse {
    transition: all 0.3s ease;
    filter: invert(1);

}</style>
