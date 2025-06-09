<script>
	let { children } = $props();
</script>

<div class="wrapper">
	{@render children()}
</div>

<style>
	.wrapper {
		display: grid;
		place-items: center;
		gap: var(--size-4);
	}
</style>
