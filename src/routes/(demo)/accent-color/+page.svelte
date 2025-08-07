<script lang="ts">
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/mdn-css_properties_accent-color';
	let color = $state('');
</script>

<label
	><code>accent-color:</code>
	<input type="color" bind:value={color} />
</label>
<div style:accent-color={color}>
	<input type="checkbox" checked />
	<input type="radio" checked />
	<input type="range" />
</div>
