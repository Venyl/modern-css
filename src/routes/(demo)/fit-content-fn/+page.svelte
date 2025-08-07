<script lang="ts">
	import Explanation from '$lib/components/Explanation.svelte';
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href =
		'https://caniuse.com/mdn-css_properties_grid-template-rows_fit-content';
</script>

<Explanation>
	{#snippet content()}
		Funkcja ta jest równoważna z następującym wyrażeniem: <code
			>min(max-content, max(min-content, {'<argument>'}))</code
		>.
		<br />
		W efekcie implikuje to 3 reguły:
		<br />
		- Element nie będzie mniejszy niż <code>min-content</code>,
		<br />
		- Element nie będzie większy niż rozmiar podany w argumencie,
		<br />
		- Element będzie rósł, żeby osiągnąć swój naturalny rozmiar,
		<br /><br />
		Jeśli nie podamy argumentu, funkcja ta zachowa się jak keyword <code>fit-content</code>.
		<br /><br />
		Jest ona zaimplementowana tylko dla kolumn grida, aby uzyskać dany efekt w innych sytuacjach wystarczy
		użyć
		<code>min-width</code>
		i <code>max-width</code>.
	{/snippet}
</Explanation>

<section>
	<p>
		Mój rozmiar to <code>fit-content(10ch)</code> ale fajnie
	</p>
</section>

<style>
	section {
		outline: 2px solid black;
		padding: var(--size-3);
		display: grid;
		grid-template-columns: fit-content(20ch);

		p {
			outline: 1px dashed black;
		}
	}
</style>
