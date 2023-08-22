<script setup>
	import { reactive, ref } from 'vue';

	const isActiveArray = ref([1]);

	let circles = reactive([
		{ number: 1, isActive: true },
		{ number: 2, isActive: '' },
		{ number: 3, isActive: '' },
		{ number: 4, isActive: '' },
	]);

	const prevStep = () => {
		isActiveArray.value.pop();
	};
	const nextStep = num => {
		isActiveArray.value = [...isActiveArray.value, isActiveArray.value.length + num];
	};
	const progressWidth = () => {
		if (isActiveArray.value.length === 2) {
			return 'width: 33%;';
		} else if (isActiveArray.value.length === 3) {
			return 'width: 66%;';
		} else if (isActiveArray.value.length === 4) {
			return 'width: 100%;';
		} else {
			return 'width: 0%;';
		}
	};
</script>

<template>
	<main class="progress-steps">
		<div class="progress__container">
			<div class="progress" id="progress" :style="progressWidth()"></div>
			<div
				class="circle"
				v-for="{ number } in circles"
				:key="number"
				:class="{
					active: isActiveArray.length > number || isActiveArray.length === number,
				}"
			>
				{{ number }}
			</div>
		</div>

		<div class="progress__container-btn">
			<button
				ref="prev"
				class="btn"
				:class="{ active: isActiveArray.length > 1 }"
				@click="prevStep"
			>
				Prev
			</button>
			<button
				ref="next"
				class="btn"
				:class="{ active: isActiveArray.length >= 1 && isActiveArray.length < 4 }"
				@click="nextStep(1)"
			>
				Next
			</button>
		</div>
	</main>
</template>

<style scoped>
	/*  */
</style>
