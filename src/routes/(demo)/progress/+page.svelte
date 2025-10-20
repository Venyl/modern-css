<script lang="ts">
	import Explanation from '$lib/components/Explanation.svelte';
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/mdn-css_types_progress';
</script>

<Explanation>
	{#snippet content()}
		Funkcja <code>progress()</code> przyjmuje 3 wartości liczbowe (nawet calc() lub wymiary jak 300ms,
		czy)
	{/snippet}
</Explanation>
