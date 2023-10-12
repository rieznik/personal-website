<script>
	import icon from '$lib/images/mail-icon.svg';
	import external from '$lib/images/external-icon.svg';
</script>

<a class="wrapper" href="mailto:rieznik.k@gmail.com" target="_blank">
	<img class="external" src={external} alt="External link icon" />
	<img class="icon" src={icon} alt="Mail icon" />
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

	.icon {
		min-width: 40%;
	}
</style>
