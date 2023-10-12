<script>
	import icon from '$lib/images/notes-icon.svg';
	import external from '$lib/images/external-icon.svg';
</script>

<a class="wrapper" href="/">
	<img class="external" src={external} alt="external link icon" />
	<img class="icon" src={icon} alt="Notes icon" />
	<p>A collection of notes on web dev topics which I found useful or inspirational</p>
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

	.icon {
		height: 20%;
	}
</style>
