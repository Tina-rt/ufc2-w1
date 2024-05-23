<template>
    <div
        class="btn px-7 py-4 bg-white text-black rounded-3xl hover:bg-gray-200 font-bold    "
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

</style>
