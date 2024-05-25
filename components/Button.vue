<template>
    <div
        class="btn px-7 py-3 bg-white text-black rounded-3xl hover:bg-gray-200     "
        :class="`btn-${severity}`"
    >
        {{ text }}
    </div>
</template>

<script lang="ts" setup>
const props = defineProps({
    text: String,
    severity: {
        type: String,
        default: "primary",
    },
});
</script>

<style>
    .btn{
        font-weight: 500;
        min-width: 140px;
        text-align: center;
    }
</style>
