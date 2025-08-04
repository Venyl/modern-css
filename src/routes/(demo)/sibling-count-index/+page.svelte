<script lang="ts">
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href =
		'https://caniuse.com/mdn-css_types_sibling-count,mdn-css_types_sibling-index';
</script>

<section>
	<div>Mój <code>sibling-index()</code> to 1, a mój <code>sibling-count()</code> to 3</div>
	<div>Mój <code>sibling-index()</code> to 2, a mój <code>sibling-count()</code> to 3</div>
	<div>Mój <code>sibling-index()</code> to 3, a mój <code>sibling-count()</code> to 3</div>
</section>

<style>
	section {
		outline: 2px solid black;
		padding: var(--size-5);
		display: grid;
		gap: var(--size-3);
	}

	div {
		padding: var(--size-2);
		outline: 1px dashed var(--gray-9);
	}
</style>
