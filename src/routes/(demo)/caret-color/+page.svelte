<script lang="ts">
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/css-caret-color';
	let color = $state('');
</script>

<label
	><code>caret-color:</code>
	<input type="color" bind:value={color} />
</label>

<div style:caret-color={color}>
	<input placeholder="napisz coś" />
</div>

<style>
	input {
		outline: 1px solid black;
	}
</style>
