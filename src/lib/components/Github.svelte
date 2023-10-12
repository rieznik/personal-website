<script>
	import logo from '$lib/images/github-logo.svg';
	import external from '$lib/images/external-icon.svg';
</script>

<a class="wrapper" href="https://github.com/rieznik" target="_blank">
	<img class="external" src={external} alt="external link icon" />
	<img class="logo" src={logo} alt="GitHub logo" />
	<p>Explore my projects on GitHub, each accompanied by its own detailed README</p>
</a>

<style>
	.wrapper {
		display: block;
		text-decoration: none;
		color: inherit;
		height: 100%;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: 50px;

		padding: 2rem;
	}

	.external {
		position: absolute;
		right: 1.2rem;
		top: 1.2rem;
	}

	.logo {
		height: 20%;
	}
</style>
