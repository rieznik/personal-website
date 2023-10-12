<script>
	import src from '$lib/images/photo.jpg';
</script>

<div class="wrapper">
	<img {src} alt="Kateryna Rieznik" class="photo" />
	<h1>Hi, I'm <span class="name">Kateryna</span>, a developer from Ukraine</h1>
	<p>Svelte enthusiast ✨ Simple human ✨ Lifelong learner</p>
</div>

<style>
	.wrapper {
		height: 100%;
		padding: 2rem;
		display: flex;
		flex-direction: column;
		justify-content: end;
		gap: 1.5rem;
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
</style>
