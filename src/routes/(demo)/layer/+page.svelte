<script lang="ts">
	import Codeblock from '$lib/components/Codeblock.svelte';
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/mdn-css_at-rules_layer';
</script>

<Codeblock>
	{#snippet code()}
		<div style:color="var(--gray-6)">
			/* NAJMNIEJSZE priority mają style w layer1, potem w layer2, potem style bez layera */
		</div>
		<div><span>@layer</span> layer1, layer2;</div>
		<div><span>@layer</span> layer1 {'{ }'}</div>
		<div><span>@layer</span> layer2 {'{ }'}</div>

		<div></div>

		<div style:color="var(--gray-6)">/* Można importować pliki do layerów */</div>
		<div><span>@import</span> "theme.css" layer(utilities);</div>

		<div></div>

		<div style:color="var(--gray-6)">/* Layery da się zagnieżdżać */</div>
		<div><span>@layer</span> layer3a {'{'}</div>
		<div>&nbsp;&nbsp;<span>@layer</span> layer3b {'{ }'}</div>
		<div>}</div>
	{/snippet}
</Codeblock>

<style>
	span {
		color: var(--pink-6);
	}
</style>
