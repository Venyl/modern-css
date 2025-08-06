<script lang="ts">
	import Explanation from '$lib/components/Explanation.svelte';
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href =
		'https://caniuse.com/mdn-css_properties_width_stretch,mdn-css_properties_height_stretch,mdn-css_properties_min-width_stretch,mdn-css_properties_max-width_stretch,mdn-css_properties_min-height_stretch,mdn-css_properties_max-height_stretch';
</script>

<Explanation>
	{#snippet content()}
		Rozmiar <code>stretch</code> wypełnia containing block tak jak wartość 100%, ale używa margin
		boxa zamiast boxa zdefiniowanego przez <code>border-box</code>, przez co nie powoduje overflowa,
		gdy element ma marginesy.
	{/snippet}
</Explanation>

<section>
	<div class="a">Mam margines i width: 100%</div>
	<div class="b">Mam margines i width: stretch</div>
</section>

<style>
	section {
		display: grid;
		gap: var(--size-3);
		/*padding: var(--size-3);*/
		outline: 2px solid black;
		div {
			margin-inline: var(--size-3);
			outline: 1px dashed black;
		}

		.a {
			width: 100%;
		}

		.b {
			width: stretch;
		}
	}
</style>
