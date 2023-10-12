<script>
	import bg from '$lib/images/bg-main.webp';

	let cursorPosition = { x: 0, y: 0 };

	const handlePointermove = (e) => {
		setTimeout(() => {
			cursorPosition = { x: e.clientX, y: e.clientY };
		}, 100);
	};
</script>

<div class="background" on:pointermove={handlePointermove}>
	<div
		class="spotlight"
		style="background: radial-gradient(circle at {cursorPosition.x}px {cursorPosition.y}px, #00000000 10px, #000000ee 350px);"
	/>
	<p style="color: white;">Cursor position {cursorPosition.x} & {cursorPosition.y}</p>
</div>

<style>
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
	}
</style>
