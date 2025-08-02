<script lang="ts">
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/mdn-css_properties_paint-order';
</script>

<svg xmlns="http://www.w3.org/2000/svg" width="400" height="200">
	<text x="10" y="75">{'<text>'} z paint-order: fill stroke</text>
	<text x="10" y="150">{'<text>'} z paint-order: stroke fill</text>
</svg>

<style>
	text {
		font-size: 30px;
		font-weight: 900;
		letter-spacing: -3px;
		stroke: red;
		stroke-width: 3px;
	}

	text:last-of-type {
		paint-order: stroke fill;
	}
</style>
