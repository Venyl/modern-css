<script lang="ts">
	import Codeblock from '$lib/components/Codeblock.svelte';
	import Explanation from '$lib/components/Explanation.svelte';
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href =
		'https://caniuse.com/mdn-css_properties_grid-template-rows_fit-content';
</script>

<Explanation>
	{#snippet content()}
		Deklaracja <code>@property</code> składa się z 3 deskryptorów:
		<br />
		-
		<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@property/syntax"
			><code>syntax</code></a
		>
		<br />
		- <code>inherits</code> (czy dzieci dziedziczą tą zmienną)
		<br />
		- <code>initial-value</code> (wartość domyślna, opcjonalna dla <code>syntax</code>'u o wartości
		<code>"*"</code>)
		<br />
		Nieznane deskryptory są ignorowane i nie unieważniają owej deklaracji.
	{/snippet}
</Explanation>

<Codeblock>
	{#snippet code()}
		<div><span style:color="var(--pink-6)">@property</span> --font-size {'{'}</div>
		<div>&nbsp;&nbsp;syntax: {"'<percentage>'"};</div>
		<div>&nbsp;&nbsp;inherits: false;</div>
		<div>&nbsp;&nbsp;initial-value: 100%;</div>
		<div>}</div>
		<div></div>
		<div><span style:color="var(--pink-6)">@keyframes</span> pulse {'{'}</div>
		<div>&nbsp;&nbsp;to {'{'}</div>
		<div>&nbsp;&nbsp;&nbsp;&nbsp;--font-size: 300%;</div>
		<div>&nbsp;&nbsp;{'}'}</div>
		<div>}</div>
		<div></div>
		<div>p {'{'}</div>
		<div>&nbsp;&nbsp;animation: pulse 1s infinite alternate;</div>
		<div>&nbsp;&nbsp;font-size: var(--font-size);</div>
		<div>}</div>
	{/snippet}
</Codeblock>

<p>Animowalne custom property</p>

<style>
	@property --font-size {
		syntax: '<percentage>';
		inherits: false;
		initial-value: 100%;
	}

	p {
		animation: pulse 1s infinite alternate;
		font-size: var(--font-size);
	}

	@keyframes pulse {
		to {
			--font-size: 300%;
		}
	}
</style>
