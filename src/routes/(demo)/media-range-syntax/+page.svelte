<script>
	import Codeblock from '$lib/components/Codeblock.svelte';
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/css-media-range-syntax';
</script>

<Codeblock>
	{#snippet code()}
		<div style:color="var(--gray-6)">// Przykładowe zastosowanie</div>
		<div><span>@media</span> (width &lt; 768px) {'{ }'}</div>
		<div><span>@media</span> (768px &lt; width &lt; 1024px) {'{ }'}</div>
		<div><span>@media</span> (1000px =&gt; height) {'{ }'}</div>
	{/snippet}
</Codeblock>

<style>
	span {
		color: var(--pink-6);
	}
</style>
