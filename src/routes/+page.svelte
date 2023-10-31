<script>
	import { Gradient } from '$lib/assets/js/gradient';
	import { onMount } from 'svelte';
	import logo from '$lib/assets/images/aft-logo.png';
	import date from '$lib/assets/images/date.png';

	onMount(() => {
		const gradient = new Gradient();
		gradient.initGradient('#gradient-canvas');
	});
</script>

<canvas id="gradient-canvas" data-transition-in />

<div class="relative w-full h-screen">
	<div class="absolute w-full h-full top-0 flex justify-center">
		<img id="logo" class="w-full lg:w-1/2 object-contain fixed top-1/3" src={logo} alt="" />
	</div>
</div>

<div class="relative w-full h-screen">
	<div class="absolute w-full h-full top-0 flex justify-center">
		<img id="date" class="w-full lg:w-1/2 object-contain fixed top-1/3 px-5" src={date} alt="" />
	</div>
</div>

<style>
	@keyframes logo {
		from {
			opacity: 1;
		}
		to {
			opacity: 0;
		}
	}

	@keyframes date {
		from {
			opacity: 0;
		}
		to {
			opacity: 1;
		}
	}

	#logo {
		opacity: 0;
		animation-name: logo;
		animation-timing-function: linear;
		animation-timeline: scroll(root block);
		animation-range: 0 50vh;
	}

	#date {
		opacity: 0;
		animation-name: date;
		animation-timing-function: linear;
		animation-timeline: scroll(root block);
		animation-range: 50vh 100vh;
	}

	#gradient-canvas {
		position: fixed;
		height: 100%;
		width: 100%;
		--gradient-color-1: #ab21ff;
		--gradient-color-2: #5b21ff;
		--gradient-color-3: #21d7ff;
		--gradient-color-4: #ff218c;
	}
</style>
