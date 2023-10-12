<script lang="ts">
	export let areaName: String;
</script>

<div class="tile" style="grid-area: {areaName}">
	<slot />
</div>

<style>
	.tile {
		backdrop-filter: blur(20px);
		width: 100%;
		height: 100%;
		background: rgba(0, 59, 124, 0.1);
		border: 1px solid rgba(255, 255, 255, 0.2);
		border-radius: 30px;
	}
</style>
