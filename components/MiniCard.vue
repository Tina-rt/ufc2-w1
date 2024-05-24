<template>
    <div class="list-element flex p-2 gap-4">
        <div class="circle-blue  mt-4">

        </div>
        <div class="flex flex-col">
            <h3 class="text-2xl">{{ props.title }}</h3>
            <p>{{ props.description }}</p>
        </div>
    </div>
</template>

<script lang="ts" setup>
const props = defineProps({
    title: {
        type: String,
        required: true
    },
    description: {
        type: String,
        required: true
    }
})
</script>

<style scoped >

.circle-blue{
    max-width: 20px;
    min-width: 20px;
    max-height: 20px;
    min-height: 20px;
    border-radius: 50%;
    background-color: #C507ED;
}
.list-element {
    position: relative;
    padding: 16px;
    border-radius: 20px;
    background: white;
    overflow: hidden;
}

.list-element::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    border-radius: 20px;
    padding: 1px;
    background: linear-gradient(to right, white, #E5E5E5);
    -webkit-mask:
        linear-gradient(#fff 0 0) content-box,
        linear-gradient(#fff 0 0);
    -webkit-mask-composite: destination-out;
    mask-composite: exclude;

}
</style>

