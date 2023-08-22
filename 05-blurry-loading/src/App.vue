<script setup>
	import { computed, onMounted, ref } from 'vue';

	const textCount = ref(0);
	const blurCount = ref(100);

	const counterText = () => {
		let timeId = setInterval(() => {
			textCount.value++;
		}, 40);
		setTimeout(() => {
			clearInterval(timeId);
		}, 4120);
	};
	const counterBlur = () => {
		let timeId = setInterval(() => {
			blurCount.value--;
		}, 40);
		setTimeout(() => {
			clearInterval(timeId);
		}, 4120);
	};
	const opacityCount = computed(() => blurCount.value / 50);

	onMounted(() => {
		counterText();
		counterBlur();
	});
</script>

<template>
	<section class="bg" :style="`filter:blur(${blurCount}px)`"></section>
	<div class="loading-text" :style="`opacity:${opacityCount}`">{{ textCount }}%</div>
</template>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Ubuntu:wght@400;500;700&display=swap');

	*,
	*::before,
	*::after {
		box-sizing: border-box;
		margin: 0;
		padding: 0;
		font-weight: normal;
	}
	#app {
		max-width: 1920px;
		margin: 0 auto;
		font-weight: normal;
	}
	body {
		font-family: 'Ubuntu', sans-serif;
		display: flex;
		align-items: center;
		justify-content: center;
		height: 100vh;
		overflow: hidden;
		margin: 0;
	}
	.bg {
		background: url('/bg-image.jpg') no-repeat center center/cover;
		position: absolute;
		top: -40px;
		left: -40px;
		width: calc(100vw + 80px);
		height: calc(100vh + 80px);
		z-index: -1;
		filter: blur(0px);
	}

	.loading-text {
		font-size: 50px;
		color: #fff;
	}
</style>
