<script lang="ts">
	export let areaName: String;
</script>

<div class="tile" style="grid-area: {areaName}" />

<style>
	.tile {
		width: 100%;
		height: 100%;
		border-radius: 30px;
		border: 1px solid rgba(255, 255, 255, 0.2);
		background: rgba(0, 59, 124, 0.1);
		backdrop-filter: blur(20px);
	}
</style>
