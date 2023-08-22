<script setup>
	import { reactive } from 'vue';

	const panels = reactive([
		{ id: 1, image: 'carousel1.jpg', title: 'Toscani', isActive: 'active' },
		{ id: 2, image: 'carousel2.jpg', title: 'Sunny beach', isActive: '' },
		{ id: 3, image: 'carousel3.jpg', title: 'Big train bridge', isActive: '' },
		{ id: 4, image: 'carousel4.jpg', title: 'Golf Bay', isActive: '' },
		{ id: 5, image: 'carousel5.jpg', title: 'Lonely tree', isActive: '' },
	]);

	const toggleActive = id => {
		const activePanel = panels.filter(panel => panel.id === id);
		allInactive();
		activePanel[0].isActive = 'active';
	};
	const allInactive = () => {
		panels.forEach(panel => {
			panel.isActive = '';
		});
	};
</script>

<template>
	<h1>Expanding Cards</h1>
	<main class="container">
		<div
			class="panel"
			v-for="{ id, image, title, isActive } in panels"
			:key="id"
			:style="{ backgroundImage: `url(${image})` }"
			:class="isActive"
			@click="toggleActive(id)"
		>
			<h3>{{ title }}</h3>
		</div>
	</main>
</template>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Muli:wght@400;500;700&display=swap');

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
	}
	body {
		height: 100vh;
		line-height: 1.6;
		font-family: 'Muli', sans-serif;
		font-size: 15px;
		display: flex;
		align-items: center;
		justify-content: center;
		overflow: hidden;
		margin: 0 auto;
		color: #fff;
	}
	.container {
		display: flex;
		width: 90vw;
	}
	h1 {
		margin: -30px 0 20px 0;
		font-weight: 700;
		text-align: center;
		color: #000;
	}
	.panel {
		position: relative;
		height: 80vh;
		background-size: cover;
		background-position: center;
		background-repeat: no-repeat;
		border-radius: 50px;
		margin: 0 10px;
		cursor: pointer;
		border: 0.5px solid #c3c3c3;
		font-weight: bold;
		flex: 0.3;
		transition: flex 0.7s ease-out;
	}
	.panel h3 {
		font-size: 24px;
		font-weight: 600;
		position: absolute;
		bottom: 20px;
		left: 30px;
		margin: 0;
		opacity: 0;
		transition: opacity 0.7s ease-in;
	}
	.panel.active {
		flex: 5;
	}
	.panel.active h3 {
		opacity: 1;
	}
	@media (max-width: 480px) {
		.container {
			width: 96vw;
		}

		.panel {
			margin: 0 6px;
		}
		.panel:nth-of-type(4),
		.panel:nth-of-type(5) {
			display: none;
		}
		.panel h3 {
			font-size: 22px;
		}
	}
</style>
