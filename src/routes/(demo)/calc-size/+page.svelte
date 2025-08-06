<script lang="ts">
	import Codeblock from '$lib/components/Codeblock.svelte';
	import Explanation from '$lib/components/Explanation.svelte';
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/mdn-css_types_calc-size';
</script>

<Explanation>
	{#snippet content()}
		Funkcja <code>calc-size()</code> działa jak <code>calc()</code>, ale pozwala używać keywordy
		jako wartości.
		<br /><br />
		Funkcja ta nakłada również na nasz selektor automatycznie
		<code>interpolate-size: allow-keywords</code>, lecz jeśli nie wykonujemy żadnych kalkulacji,
		lepiej użyć po prostu <code>interpolate-size</code>.
		<br /><br />
		<code>calc-size()</code> nie pozwala na animowanie rozmiaru między dwoma keywordami, ani na
		używanie dwóch keywordów w jednej kalkulacji.
		<br /><br />
		Pierwszy argument to intrinsic size value:
		<br />
		- <code>auto</code>
		<br />
		- <code>min-content</code>, <code>max-content</code>, <code>fit-content</code>
		<br />
		- <code>content</code> (dla elementów z <code>flex-basis</code>)
		<br />
		- inny <code>calc-size()</code> lub <code>calc()</code>
		<br /><br />
		Drugi argument to kalkulacja, w której specjalny keyword <code>size</code> odpowiada pierwszemu argumentowi.
	{/snippet}
</Explanation>

<Codeblock>
	{#snippet code()}
		<div style:color="var(--gray-6);">
			// Szerokość sekcji to dwukrotność długośći najdłuższego słowa
		</div>
		<div>section {'{'}</div>
		<div>&nbsp;&nbsp;width: calc-size(min-content, size * 2);</div>
		<div>}</div>
	{/snippet}
</Codeblock>

<section><span>Abcabcabc</span> abcabc abc</section>

<style>
	section {
		outline: 1px solid red;
		width: calc-size(min-content, size * 2);

		span {
			outline: 1px solid blue;
		}
	}
</style>
