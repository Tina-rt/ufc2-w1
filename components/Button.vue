<template>
    <div
        class="btn px-7 py-3 text-black rounded-3xl hover:bg-gray-200     "
        :class="`btn-${severity}`"
    >
        {{ text }}
    </div>
</template>

<script lang="ts" setup>
const props = defineProps({
    text: String,
    severity: {
        type: String as PropType<"primary" | "secondary">,
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
    .btn-primary{
        background: white;
    }
    .btn-secondary{
        background: transparent;
        border: 1px solid white;
    }
</style>
