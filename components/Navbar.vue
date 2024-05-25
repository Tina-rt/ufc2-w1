<template>
    <div class="navbar text-white px-20 py-5">
        <div class="navbar-item  flex-col flex justify-start items-start flex-grow " :class="{'filter-inverse': isScrolled}">
            <Logo />
        </div>
        <div class="navbar-item nav-items justify-center items-center  " :class="{'filter-inverse': isScrolled}">
            <div class="nav-item">Services</div>
            <div class="nav-item">Pricing</div>
            <div class="nav-item">Drones</div>
            <div class="nav-item">Contact us</div>
            <div class="nav-item">About us</div>
        </div>
        <div class="navbar-item button-group items-center flex-grow justify-end">
            <Button text="Login" severity="primary" />
            <Button text="Register" severity="secondary" />
        </div>
    </div>
</template>

<script lang="ts" setup>
import { ref, onMounted, onUnmounted } from 'vue';

const isScrolled = ref(false);

const handleScroll = () => {
    const scrollPosition = window.scrollY;
    isScrolled.value = scrollPosition > window.innerHeight; // 100vh
    console.log(isScrolled.value)
};

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
    grid-template-columns: 1fr 2fr 1fr;
    // z-index: 0;
    // background: linear-gradient(to bottom, rgba(255, 255, 255, 0.342), rgba(255, 255, 255, 0.247));
    backdrop-filter: blur(30px);
    mask-image: linear-gradient(180deg, rgba(255,255,255,1) 0%, rgba(255,255,255,0.6054796918767507) 86%, rgba(255,255,255,0) 100%);
    transition: all 0.5s ease;
}
.navbar:hover{
    backdrop-filter: blur(20px);
    cursor: pointer;
}
.navbar-item{
    transition: all 0.5s ease;
}
.nav-item{
    transition: all 0.3s ease;
}
.nav-items {
    display: flex;
    gap: 40px;
    font-size: 1.2rem;
    font-weight: 300;
    min-width: fit-content
}

.button-group {
    display: flex;
    flex-direction: row;
    gap: 10px;
}

.navbar .brand {
    width: 50px;
    height: 50px;
}

.filter-inverse{
    transition: all 0.3s ease;
    filter: invert(1);

}
</style>
