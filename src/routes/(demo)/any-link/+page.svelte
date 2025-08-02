<script lang="ts">
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/css-any-link';
</script>

<div>W skrócie to samo co <code>a[href], area[href]</code></div>
