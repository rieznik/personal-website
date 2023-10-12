<script>
	import src from '$lib/images/photo.jpg';
	import { spring } from 'svelte/motion';

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
			<Tile areaName="about">
				<img {src} alt="Kateryna Rieznik" class="photo" />
				<h1>Hi, I'm <span class="name">Kateryna</span>, a developer from Ukraine</h1>
				<p>Svelte enthusiast ✨ Simple human ✨ Lifelong learner</p>
			</Tile>
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
		display: grid;
		gap: 1rem;
		grid-template-rows: repeat(3, 280px);
		grid-template-columns: repeat(4, 280px);
		grid-template-areas: 'about about ukraine notes' 'about about github notes' 'mail theme github linkedin';
		padding-top: 100px;
	}

	.photo {
		width: 128px;
		height: 128px;
		border-radius: 50%;
	}

	h1 {
		font-size: 1rem;
	}

	.name {
		font-size: 2rem;
	}

	.background {
		width: 100vw;
		height: 100vh;
		background-image: url('$lib/images/bg-main.webp');
		background-repeat: no-repeat;
		background-position: center;
		background-size: cover;
	}

	.spotlight {
		pointer-events: none;
		position: fixed;
		top: 0;
		left: 0;
		opacity: 1;
		width: 100vw;
		height: 100vh;
		animation: pulse 3s ease-in-out infinite alternate forwards;
		background: #000000ee;
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
