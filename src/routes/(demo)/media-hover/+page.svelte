<script lang="ts">
	import Explanation from '$lib/components/Explanation.svelte';
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/mdn-css_at-rules_media_hover';
</script>

<Explanation>
	{#snippet content()}
		Przeglądarka zaaplikuje style umieszone wewnątrz <code>@media (hover) {'{ ... }'}</code> tylko
		jeśli użytkownik jest w stanie hoverować elementy.
		<br /><br />
		Da się odwrócić ten warunek pisząc <code>@media not (hover) {'{ ... }'}</code>
	{/snippet}
</Explanation>
<div class="has-hover">
	Posiadasz możliwośc hoverowania elementów. Sprawdź tą stronę na telefonie.
</div>
<div class="has-no-hover">
	Nie posiadasz możliwości hoverowania elementów. Sprawdź tą stronę na komputerze.
</div>

<style>
	.has-hover,
	.has-no-hover {
		display: none;
	}

	@media (hover) {
		.has-hover {
			color: var(--green-9);
			display: block;
		}
	}

	@media not (hover) {
		.has-no-hover {
			color: var(--red-9);
			display: block;
		}
	}
</style>
