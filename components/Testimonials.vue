<template>
	<div class="testimonials w-full py-10">
		<SectionTitle title="Testimonials" subtitle="What People Says" />
		<div ref="testimonialsListRef"
			class="testimonials-list flex justify-start  items-center gap-0 overflow-x-scroll overflow-y-hidden">
			<TestimonialCard class="testimonialCard" v-for="testimonial in testimonials" :key="testimonial.author"
				:testimonial="testimonial" />
		</div>
		<div class="scroll-bar-controller flex justify-center items-center gap-4 p-5">
			<div v-for="testimonial in testimonials" :key="testimonial.author"
				class="dot w-2 h-2 bg-[#b6b5b6] rounded-full">
			</div>
		</div>
	</div>
</template>

<script lang="ts" setup>

const testimonials = ref([
	{
		image: "https://images.unsplash.com/photo-1607346256330-dee7af15f7c5?q=80&w=1000&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8aW5kaWFuJTIwbWFufGVufDB8fDB8fHww",
		quote: "The customer service at this company is outstanding. They really go above and beyond to ensure customer satisfaction.",
		author: "John Doe",
		authorFunction: "CEO, Company",
	},
	{
		image: "https://images.pexels.com/photos/1208015/pexels-photo-1208015.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500",
		quote: "I recently bought the DJI Mini 2, and I'm absolutely thrilled with its performance. It's lightweight, easy to maneuver, and captures stunning footage.",
		author: "John Doe",
		authorFunction: "CEO, Company",
	},
	{
		image: "https://img.freepik.com/free-photo/smiley-man-with-headphones-front-view_23-2149915903.jpg?size=626&ext=jpg&ga=GA1.1.2082370165.1716595200&semt=ais_user",
		quote: "I recently bought the DJI Mini 2, and I'm absolutely thrilled with its performance. It's lightweight, easy to maneuver, and captures stunning footage.",
		author: "John Doe",
		authorFunction: "CEO, Company",
	},
]);



import { onMounted, ref } from 'vue';

const testimonialsListRef = ref<HTMLDivElement | null>(null);

onMounted(() => {
	if (testimonialsListRef.value) {
		const list = testimonialsListRef.value;
		const updateScrollPosition = () => {
			const maxScrollLeft = list.scrollWidth - list.clientWidth;
			list.scrollLeft = maxScrollLeft / 2;
		};
		updateScrollPosition();
		window.addEventListener('resize', updateScrollPosition);
		onUnmounted(() => {
			window.removeEventListener('resize', updateScrollPosition);
		});

		list.children[0].classList.add('shrinkone');
		list.children[1].classList.add('grow');
		list.children[2].classList.add('shrinktwo');

		let scrollStep =list.clientWidth / 4;
		setInterval(() => {
			if (list) {
				list.scrollLeft += scrollStep;
				if (list.scrollLeft >= list.scrollWidth - list.clientWidth) {
					list.scrollLeft = 0;
				}
			}
		}, 2000);

		let currentScrollLeft = testimonialsListRef.value.scrollLeft;
		// testimonialsListRef.value.addEventListener('scroll', () => {
		// 	const handleScroll = () => {
		// 		if (testimonialsListRef.value) {
		// 			const newScrollLeft = testimonialsListRef.value.scrollLeft;
		// 			console.log("newscrollleft", newScrollLeft, "current scroll left", currentScrollLeft)
		// 			if (newScrollLeft >= currentScrollLeft ) {
		// 				testimonialsListRef.value.children[2].classList.remove('shrink');
		// 				testimonialsListRef.value.children[2].classList.add('grow');
		// 				console.log('Scrolled Right');
		// 			}
		// 			else if (newScrollLeft < currentScrollLeft) {
		// 				console.log('Scrolled Left');
		// 			}
		// 			currentScrollLeft = newScrollLeft; // Update the current scroll position
		// 		}
		// 	};
		// 	handleScroll(); // Call the function to handle initial comparison
		// })
	}
});

</script>

<style scoped lang="scss">
@keyframes grow {
	0% {
		opacity: 0.5;
		transform: scale(0.8);
	}
	50% {
		opacity: 1;
		transform: scale(1);
	}
	100% {
		opacity: 0.5;
		transform: scale(0.8);
	}
}

@keyframes shrinkone {
	0% {
		opacity: 1;
		transform: scale(1);
	}
	100% {
		opacity: 0.5;
		transform: scale(0.8);
	}
	
}
@keyframes shrinktwo {
	0% {
		opacity: 0.5;
		transform: scale(0.8);
	}
	50% {
		opacity: 0.5;
		transform: scale(0.8);
	}
	100% {
		opacity: 1;
		transform: scale(1);
	}
	
}

.testimonials-list {
	width: 100%;
	overflow-x: scroll;
	scroll-behavior: smooth;
	padding-inline: 400px;

}

.testimonialCard {
	opacity: 0.5;
	transform: scale(0.8);
}

.grow {
	animation: grow 2s ease;
	animation-timeline: scroll(x);
}

.shrinkone {
	animation: shrinkone 2s ease;
	animation-timeline: scroll(x);
}

.shrinktwo {
	animation: shrinktwo 2s ease;
	animation-timeline: scroll(x);
}

.testimonials-list::-webkit-scrollbar {
	// display: none;
}

.testimonials-list {
	// -ms-overflow-style: none;
	// /* IE and Edge */
	scrollbar-width: none;
	/* Firefox */
}
</style>

