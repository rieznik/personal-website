<script>
	import { spring } from 'svelte/motion';

	import Tile from '$lib/components/Tile.svelte';
	import About from '$lib/components/About.svelte';
	import Ukraine from '$lib/components/Ukraine.svelte';
	import Linkedin from '$lib/components/Linkedin.svelte';
	import Github from '$lib/components/Github.svelte';
	import Mail from '$lib/components/Mail.svelte';
	import Notes from '$lib/components/Notes.svelte';
	import Theme from '$lib/components/Theme.svelte';

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
				<About />
			</Tile>
			<Tile areaName="ukraine">
				<Ukraine />
			</Tile>
			<Tile areaName="notes">
				<Notes />
			</Tile>
			<Tile areaName="github">
				<Github />
			</Tile>
			<Tile areaName="linkedin">
				<Linkedin />
			</Tile>
			<Tile areaName="mail">
				<Mail />
			</Tile>
			<Tile areaName="theme">
				<Theme />
			</Tile>
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

	.background {
		width: 100vw;
		height: 100vh;
		background-image: url('$lib/images/bg-main.webp');
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
