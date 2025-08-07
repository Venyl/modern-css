<script lang="ts">
	import Codeblock from '$lib/components/Codeblock.svelte';
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/css-has';
</script>

<Codeblock>
	{#snippet code()}
		<div>:has(video):has(audio) {'{'}</div>
		<div style:color="var(--gray-6)">&nbsp;&nbsp;/* style jeśli masz i video i audio */</div>
		<div>}</div>
		<div></div>
		<div>:has(video, audio) {'{'}</div>
		<div style:color="var(--gray-6)">&nbsp;&nbsp;/* style jeśli masz albo video albo audio */</div>
		<div>}</div>
		<div></div>
		<div>:has(+ :is(h1, h2, h3)) {'{'}</div>
		<div style:color="var(--gray-6)">
			&nbsp;&nbsp;/* style jeśli następuje po tobie h1, h2 lub h3 */
		</div>
		<div>}</div>
		<div></div>
		<div>:has(+ h1, + h2, + h3) {'{'}</div>
		<div style:color="var(--gray-6)">&nbsp;&nbsp;/* to samo co wyżej */</div>
		<div>}</div>
	{/snippet}
</Codeblock>
