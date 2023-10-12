<script>
	import logo from '$lib/images/linkedin-logo.svg';
	import external from '$lib/images/external-icon.svg';
</script>

<a class="wrapper" href="https://www.linkedin.com/in/katerynarieznik" target="_blank">
	<img class="external" src={external} alt="external link icon" />
	<img src={logo} alt="LinkedIn logo" />
</a>

<style>
	.wrapper {
		display: block;
		height: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.external {
		position: absolute;
		right: 1.2rem;
		top: 1.2rem;
	}
</style>
