<template>
    <div class="navbar text-white px-20 py-5">
        <div class="navbar-item  flex-col flex justify-start items-start w-2/6 ">
            <img src="~/assets/img/logo.png" class="brand" alt="logo" />
            <span class="font-bold">DRONE</span>
        </div>
        <div class="navbar-item nav-items items-center w-2/6">
            <div class="nav-item">Services</div>
            <div class="nav-item">Pricing</div>
            <div class="nav-item">Drones</div>
            <div class="nav-item">Contact us</div>
            <div class="nav-item">About us</div>
        </div>
        <div class="navbar-item button-group items-center w-2/6 justify-end">
            <Button text="Login" severity="primary" />
            <Button text="Register" severity="secondary" />
        </div>
    </div>
</template>

<script lang="ts" setup></script>

<style scoped lang="scss">
.navbar {
    display: flex;
    flex-direction: row;
    width: 100%;
    justify-content: space-between;
    z-index: 2;
}

.nav-items {
    display: flex;
    gap: 40px;
    font-size: 18px;
    font-weight: bold;
}

.button-group {
    display: flex;
    flex-direction: row;
    gap: 10px;
}

.navbar .brand{
    width: 50px;
    height: 50px;
}
</style>
