<script setup>
	import { ref } from 'vue';

	const isOpen = ref(false);
</script>

<template>
	<main class="container">
		<div class="search" :class="{ active: isOpen }">
			<input type="text" placeholder="Search..." class="input" />
			<button class="btn" :class="{ active: isOpen }" @click="isOpen = !isOpen">
				<svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 512 512">
					<path
						d="M505 442.7L405.3 343c-4.5-4.5-10.6-7-17-7H372c27.6-35.3 44-79.7 44-128C416 93.1 322.9 0 208 0S0 93.1 0 208s93.1 208 208 208c48.3 0 92.7-16.4 128-44v16.3c0 6.4 2.5 12.5 7 17l99.7 99.7c9.4 9.4 24.6 9.4 33.9 0l28.3-28.3c9.4-9.4 9.4-24.6.1-34zM208 336c-70.7 0-128-57.2-128-128 0-70.7 57.2-128 128-128 70.7 0 128 57.2 128 128 0 70.7-57.2 128-128 128z"
					/>
				</svg>
			</button>
		</div>
		<p class="enter" :class="{ active: isOpen }">Press "Enter" to do search...</p>
	</main>
</template>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;600;700&display=swap');

	*,
	*::before,
	*::after {
		box-sizing: border-box;
		margin: 0;
		font-weight: normal;
	}
	#app {
		max-width: 1920px;
		margin: 0 auto;
		padding: 2rem;

		font-weight: normal;
	}
	body {
		background-image: linear-gradient(90deg, #7d5fff, #7158e2);
		font-family: 'Roboto', sans-serif;
		display: flex;
		align-items: center;
		justify-content: center;
		height: 100vh;
		overflow: hidden;
		margin: 0;
	}
	.container {
		position: relative;
	}
	.search {
		position: relative;
		height: 50px;
		margin-bottom: 10px;
	}
	.search .input {
		background-color: #fff;
		border: 0;
		font-size: 18px;
		padding: 15px;
		height: 50px;
		width: 50px;
		transition: width 0.4s ease;
		border-radius: 15px;
	}
	.btn {
		background-color: #fff;
		border: 0;
		cursor: pointer;
		font-size: 24px;
		border-radius: 15px;
		position: absolute;
		top: 0;
		left: 0;
		height: 50px;
		width: 50px;
		transition: transform 0.4s ease;
	}
	.btn:focus,
	.input:focus {
		outline: none;
	}
	.search.active .input {
		width: 200px;
		border-radius: 15px 0 0 15px;
	}
	.search.active .btn {
		border-radius: 0 15px 15px 0;
		transform: translateX(198px);
	}
	.enter {
		width: 200px;
		position: absolute;
		text-align: center;
		color: #b9aafa;
		font-size: 14px;
		opacity: 0;
		transition: opacity 0.4s ease-in;
	}
	.enter.active {
		opacity: 1;
	}
</style>
