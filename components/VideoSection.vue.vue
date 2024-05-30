<template>
    <div class="perspective">
        <div class="video-section">
            <div class="rec rec1"></div>
            <div class="rec rec2"></div>
            <div class="play-btn bg-white rounded-full ">
                <PlayIcon class="h-12 w-12 p-2" @click="playVideo" v-if="!videoIsPlaying" />
                <PauseIcon class="h-12 w-12 p-2" @click="pauseVideo" v-else />
            </div>
            <div class="image">
                <video loop muted ref="video" v-if="props.videoUrl" :src=props.videoUrl></video>
                <img v-if="props.image" :src=props.image alt="Video Thumb">
            </div>
        </div>
    </div>
</template>

<script lang="ts" setup>
import { PlayIcon, PauseIcon } from '@heroicons/vue/16/solid';

const props = defineProps({
    image: {
        type: String,
        required: false,
    },
    videoUrl: {
        type: String,
        required: false,
    }
});

const video = ref<HTMLVideoElement | null>(null);
const videoIsPlaying = ref(false);

const playVideo = () => {
    if (video.value) {
        video.value.play();
    }
    videoIsPlaying.value = true;
}

const pauseVideo = () => {
    if (video.value) {
        video.value.pause();
    }
    videoIsPlaying.value = false;
}

onMounted(() => {
    if (video.value) {
        video.value.currentTime = 4; // Set the video track to 4 seconds
    }
})

</script>

<style scoped lang="scss">
.video-section:hover {
    transform: rotateY(-15deg) rotateX(15deg);

    .rec {
        transform: scale(1.3);
    }

    .play-btn {
        box-shadow: 10px 5px 20px 0px rgb(31, 31, 31);
        transform: rotateY(-15deg) rotateX(15deg) translate(-100%, -100%);
    }

    .image {

        img, video {
            transform: scale(0.95);
            box-shadow: 10px 5px 20px 0px rgba(0, 0, 0, 0.5);
        }
    }

}

.perspective {
    perspective: 1000px;
}

.video-section {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    max-width: 600px;
    transition: all 0.3s ease-in-out;

    * {
        transition: all 0.4s ease-in-out;
    }

    .rec {
        width: 100px;
        height: 100px;
        background-color: #C507ED;
        border-radius: 20px;
        position: absolute;
        transform: scale(1.3);
        box-shadow: 2px 5px 10px 0px rgba(90, 90, 90, 0.5);
        z-index: -1;
        transition: all 0.3s ease;
    }

    .rec1 {
        top: 5px;
        left: 5px;
    }

    .rec2 {
        bottom: 5px;
        right: 5px;
    }

    .play-btn {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        z-index: 2;
        color: #C507ED;
        cursor: pointer;
    }

    .image {
        height: 100%;
        width: 600px;
        object-fit: cover;
        border-radius: 20px;
        @media (max-width: 768px) {
            width: 300px;
        }
        img,
        video {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 30px;
        }
    }
}
</style>