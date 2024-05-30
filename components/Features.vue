<template>
	<div class="flex w-full justify-center md:px-16 lg:px-16 px-2 flex-wrap-reverse py-2 gap-10  md:flex-nowrap" id="services">
		<div class="md:w-[50%] lg:w-[50%] w-full">
			<div class="col-content flex flex-col justify-evenly h-full flex-wrap gap-4">
				<h3 class="text-5xl text-center">
					Empowering innovation, one drone at a time
				</h3>
				<p class="" style="">
					"Empowering innovation, one drone at a time" means that through our drones, we strive to drive progress
					and creativity in various industries and applications.
				</p>
				<div class="flex gap-5">
					<a class=" text-[#C507ED] rounded-md underline-offset-4 underline">Learn More</a>
				</div>
			</div>
		</div>
		<VideoSectionVue video-url="/videos/video1.mp4" />
	</div>
	<div class="flex w-full justify-center md:px-16 lg:px-16 px-0 py-6 my-16 gap-10 flex-wrap">
		<div class="md:w-[50%] lg:w-[50%] w-full col-content flex flex-col justify-around gap-5 h-full pt-5">
			<h3 class="text-5xl text-center">
				These Are Often Considered For Drone Product Quality
			</h3>
			<p class="pb-5" style="">
				As Of My Last Update in September 2021, I Can Provide You With Three Key Factors That Are Often Considered
				For Drone Product Quality
			</p>
			<VideoSectionVue  image="https://picsum.photos/id/10/600/400" />
		</div>
		<div class="md:w-[40%] lg:w-[40%] w-full flex flex-col gap-10 flex-wrap">
			<MiniCard v-for="feature in features" :key="feature.title" :title="feature.title"
				:description="feature.description" />
		</div>
	</div>
</template>

<script lang="ts" setup>
const features = [
	{
		title: "Build Quality",
		description: "High-Quality Drones Are Usually Used Made With Robust Materials Such As Carbon Fiber, Magnesium Alloy"
	},
	{
		title: "Flight Performance",
		description: "Group Your Contacts By Location, Age, And Almost Any Behavior With Advanced Segmentation Tools"
	},
	{
		title: "Camera Quality",
		description: "Factors Such As The Sensor Size, Megapixels, Image Stabilization, And Ajustable Settings Like Aperture, Shutter Speed, And ISO"
	},
	{
		title: "Battery Life And Charging Time",
		description: "High-Quality Drones Typically Have Longer Flight Time And Allowing You To Enjoy Extened Aerial."
	}
]
</script>



