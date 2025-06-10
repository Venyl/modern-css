<script>
	import Codeblock from '$lib/components/Codeblock.svelte';
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/css-media-range-syntax';
</script>

<Codeblock>
	{#snippet code()}
		<div style:color="var(--gray-6)">// Przykładowe zastosowanie</div>
		<div>@media (width &lt; 768px) {'{ }'}</div>
		<div>@media (768px &lt; width &lt; 1024px) {'{ }'}</div>
		<div>@media (1000px =&gt; height) {'{ }'}</div>
	{/snippet}
</Codeblock>
