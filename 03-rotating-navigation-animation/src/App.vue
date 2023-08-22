<script setup>
	import { ref } from 'vue';

	const isOpen = ref(false);
</script>

<template>
	<div class="container" :class="{ 'show-nav': isOpen }">
		<div class="circle-container">
			<div class="circle">
				<button id="close" @click="isOpen = false">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						height="1em"
						viewBox="0 0 352 512"
						fill="#FFFFFF"
					>
						<path
							d="M242.72 256l100.07-100.07c12.28-12.28 12.28-32.19 0-44.48l-22.24-22.24c-12.28-12.28-32.19-12.28-44.48 0L176 189.28 75.93 89.21c-12.28-12.28-32.19-12.28-44.48 0L9.21 111.45c-12.28 12.28-12.28 32.19 0 44.48L109.28 256 9.21 356.07c-12.28 12.28-12.28 32.19 0 44.48l22.24 22.24c12.28 12.28 32.2 12.28 44.48 0L176 322.72l100.07 100.07c12.28 12.28 32.2 12.28 44.48 0l22.24-22.24c12.28-12.28 12.28-32.19 0-44.48L242.72 256z"
						/>
					</svg>
				</button>
				<button id="open" @click="isOpen = true">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						height="1em"
						viewBox="0 0 448 512"
						fill="#FFFFFF"
					>
						<path
							d="M16 132h416c8.837 0 16-7.163 16-16V76c0-8.837-7.163-16-16-16H16C7.163 60 0 67.163 0 76v40c0 8.837 7.163 16 16 16zm0 160h416c8.837 0 16-7.163 16-16v-40c0-8.837-7.163-16-16-16H16c-8.837 0-16 7.163-16 16v40c0 8.837 7.163 16 16 16zm0 160h416c8.837 0 16-7.163 16-16v-40c0-8.837-7.163-16-16-16H16c-8.837 0-16 7.163-16 16v40c0 8.837 7.163 16 16 16z"
						/>
					</svg>
				</button>
			</div>
		</div>

		<main class="content">
			<h1>Amazing Article</h1>
			<small>Francisco Zapata</small>
			<p>
				Proin velit eros, cursus dignissim ullamcorper non, iaculis ac odio. Integer eu
				malesuada sem. Sed lacinia mi ante, eget porta massa maximus ut. Sed et urna et
				mauris auctor viverra eget ut lorem. Proin tristique rutrum condimentum. Donec
				libero eros, tincidunt eget gravida posuere, posuere nec ligula. In et ex
				interdum, viverra ipsum in, pharetra odio. Cras at odio non velit efficitur
				vestibulum. Nullam congue porttitor neque. Integer sed posuere quam, quis
				tristique orci. Ut viverra commodo pretium. Duis justo sapien, consequat volutpat
				nulla sit amet, finibus bibendum nunc. In blandit, dui et luctus tristique, neque
				ipsum condimentum justo, eu.
			</p>
			<h3>My Dog</h3>
			<img src="/my-dog.jpg" alt="Puppy" />
			<p>
				Integer pellentesque ligula augue, ut efficitur turpis placerat eu. In accumsan
				consequat mi, vel venenatis elit lacinia condimentum. Praesent ac malesuada
				turpis. Cras quis tempor ipsum, eget porta est. Nam ut dapibus sem. Duis placerat
				magna at erat consectetur aliquet. Donec consectetur et elit finibus tincidunt.
				Duis venenatis sagittis eleifend. Integer porta elementum lacus quis varius. In
				hac habitasse platea dictumst. Class aptent taciti sociosqu ad litora torquent per
				conubia nostra, per inceptos himenaeos. Curabitur.
			</p>
		</main>
	</div>

	<nav>
		<ul>
			<li>
				<a href="">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						height="1em"
						viewBox="0 0 576 512"
						fill="#FFFFFF"
					>
						<path
							d="M280.37 148.26L96 300.11V464a16 16 0 0 0 16 16l112.06-.29a16 16 0 0 0 15.92-16V368a16 16 0 0 1 16-16h64a16 16 0 0 1 16 16v95.64a16 16 0 0 0 16 16.05L464 480a16 16 0 0 0 16-16V300L295.67 148.26a12.19 12.19 0 0 0-15.3 0zM571.6 251.47L488 182.56V44.05a12 12 0 0 0-12-12h-56a12 12 0 0 0-12 12v72.61L318.47 43a48 48 0 0 0-61 0L4.34 251.47a12 12 0 0 0-1.6 16.9l25.5 31A12 12 0 0 0 45.15 301l235.22-193.74a12.19 12.19 0 0 1 15.3 0L530.9 301a12 12 0 0 0 16.9-1.6l25.5-31a12 12 0 0 0-1.7-16.93z"
						/>
					</svg>
					Home
				</a>
			</li>
			<li>
				<a href="">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						height="1em"
						viewBox="0 0 512 512"
						fill="#FFFFFF"
					>
						<path
							d="M256 288c79.5 0 144-64.5 144-144S335.5 0 256 0 112 64.5 112 144s64.5 144 144 144zm128 32h-55.1c-22.2 10.2-46.9 16-72.9 16s-50.6-5.8-72.9-16H128C57.3 320 0 377.3 0 448v16c0 26.5 21.5 48 48 48h416c26.5 0 48-21.5 48-48v-16c0-70.7-57.3-128-128-128z"
						/>
					</svg>
					About
				</a>
			</li>
			<li>
				<a href="">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						height="1em"
						viewBox="0 0 512 512"
						fill="#FFFFFF"
					>
						<path
							d="M502.3 190.8c3.9-3.1 9.7-.2 9.7 4.7V400c0 26.5-21.5 48-48 48H48c-26.5 0-48-21.5-48-48V195.6c0-5 5.7-7.8 9.7-4.7 22.4 17.4 52.1 39.5 154.1 113.6 21.1 15.4 56.7 47.8 92.2 47.6 35.7.3 72-32.8 92.3-47.6 102-74.1 131.6-96.3 154-113.7zM256 320c23.2.4 56.6-29.2 73.4-41.4 132.7-96.3 142.8-104.7 173.4-128.7 5.8-4.5 9.2-11.5 9.2-18.9v-19c0-26.5-21.5-48-48-48H48C21.5 64 0 85.5 0 112v19c0 7.4 3.4 14.3 9.2 18.9 30.6 23.9 40.7 32.4 173.4 128.7 16.8 12.2 50.2 41.8 73.4 41.4z"
						/>
					</svg>
					Contact
				</a>
			</li>
		</ul>
	</nav>
</template>

<style scoped>
	/*  */
</style>
