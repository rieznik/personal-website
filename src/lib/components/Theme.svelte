<script>
	import icon from '$lib/images/toggle.svg';
</script>

<div class="wrapper">
	<button>
		<img class="icon" src={icon} alt="toggle theme icon" />
	</button>
</div>

<style>
	.wrapper {
		display: block;
		height: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	button {
		background: none;
		border: none;
	}

	.icon {
		min-width: 40%;
	}
</style>
