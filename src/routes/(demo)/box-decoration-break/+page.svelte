<script lang="ts">
	import Explanation from '$lib/components/Explanation.svelte';
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/css-boxdecorationbreak';
	let breakStyle = $state('slice');
</script>

<Explanation>
	{#snippet content()}
		Ta właściwość kontroluje renderowanie fragmentów elementu, gdy łamie się na wiele linii.
		Oddziałowuje na:
		<br />
		- <code>background</code><br />
		- <code>border</code><br />
		- <code>border-image</code><br />
		- <code>box-shadow</code><br />
		- <code>clip-path</code><br />
		- <code>margin</code><br />
		- <code>padding</code><br />
	{/snippet}
</Explanation>

<div>
	<code>box-decoration-break:</code>
	<label for="slice">
		<code>slice</code>
		<input type="radio" bind:group={breakStyle} value="slice" id="slice" />
	</label>
	<label for="clone">
		<code>clone</code>
		<input type="radio" bind:group={breakStyle} value="clone" id="clone" />
	</label>
</div>

<p>
	<span style:box-decoration-break={breakStyle}>Ale<br />brzydki<br /> ten tekst</span>
</p>

<style>
	label {
		display: inline grid;
		justify-content: center;
	}

	span {
		font-size: var(--font-size-5);
		padding: var(--size-1);
		border-radius: var(--size-3);
		line-height: 3;
		background: linear-gradient(to bottom right, lightblue, steelblue);
		border: 5px solid dodgerblue;
		box-shadow:
			8px 8px 10px 0px steelblue,
			-5px -5px 5px 0px blue;
	}
</style>
