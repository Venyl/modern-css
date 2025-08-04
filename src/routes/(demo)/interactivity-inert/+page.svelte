<script lang="ts">
	import Explanation from '$lib/components/Explanation.svelte';
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/mdn-css_properties_interactivity_inert';
</script>

<Explanation>
	{#snippet content()}
		Właściwość <code>interactivity: inert</code> jest jak atrybut <code>inert</code>, który ma
		zastosowanie jak atrybut <code>disabled</code>, ale dla elementów innych niż formularzowe.
		<br /><br />
		Sprawia, że elementu nie da się:
		<ul>
			<li>- kliknać</li>
			<li>- focusować</li>
			<li>- zaznaczyć</li>
			<li>- edytować</li>
			<li>- znaleźć używając Ctrl+F</li>
			<li>- znaleźć używając technologię asystującą</li>
		</ul>
	{/snippet}
</Explanation>

<div>Mam <code>interactivity: inert</code></div>

<style>
	div {
		interactivity: inert;
	}
</style>
