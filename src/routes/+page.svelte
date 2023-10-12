<script>
	import bg from '$lib/images/bg-main.webp';
	import { spring } from 'svelte/motion';
	import { tweened } from 'svelte/motion';

	import Tile from './Tile.svelte';

	let coords = spring(
		{ x: 50, y: 50 },
		{
			stiffness: 0.04,
			damping: 0.4
		}
	);
</script>

<div
	class="background"
	on:mousemove={(e) => {
		coords.set({ x: e.clientX, y: e.clientY });
	}}
	role="none"
>
	<div
		class="spotlight"
		style="background: radial-gradient(circle at {$coords.x}px {$coords.y}px, #00000000 10px, #000000ee 250px);"
	/>
	<div class="container">
		<div class="grid">
			<Tile areaName="about" />
			<Tile areaName="ukraine" />
			<Tile areaName="notes" />
			<Tile areaName="github" />
			<Tile areaName="linkedin" />
			<Tile areaName="mail" />
			<Tile areaName="theme" />
		</div>
	</div>
</div>

<style>
	.container {
		max-width: 1200px;
		margin: 0 auto;
	}

	.grid {
		padding-top: 100px;
		display: grid;
		gap: 1rem;
		grid-template-columns: repeat(4, 280px);
		grid-template-rows: repeat(3, 280px);
		grid-template-areas: 'about about ukraine notes' 'about about github notes' 'mail theme github linkedin';
	}

	.background {
		height: 100vh;
		width: 100vw;

		background-image: url('$lib/images/bg-main.webp');
		background-size: cover;
		background-repeat: no-repeat;
		background-position: center;
	}

	.spotlight {
		position: fixed;
		opacity: 1;
		width: 100vw;
		height: 100vh;
		top: 0;
		left: 0;
		pointer-events: none;
		background: #000000ee;
		animation: pulse 3s ease-in-out infinite alternate forwards;
	}

	@keyframes pulse {
		0% {
			transform: scale(1);
		}
		100% {
			transform: scale(1.1);
		}
	}
</style>
