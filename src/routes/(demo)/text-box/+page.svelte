<script lang="ts">
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/mdn-css_properties_text-box';

	let trim = $state('trim-both');
	let edgeStart = $state('text');
	let edgeEnd = $state('text');
</script>

<form>
	<div>
		<label for="trim">text-box-trim</label>
		<select bind:value={trim} id="trim">
			<option>trim-both</option>
			<option>trim-start</option>
			<option>trim-end</option>
		</select>
	</div>
	<div>
		<label for="edge-start">text-box-edge (start)</label>
		<select bind:value={edgeStart} id="edge-start">
			<option>text</option>
			<option>cap</option>
			<option>ex</option>
		</select>
	</div>
	<div>
		<label for="edge-start">text-box-edge (end)</label>
		<select bind:value={edgeEnd} id="edge-end">
			<option>text</option>
			<option>alphabetic</option>
		</select>
	</div>
</form>

<section>
	<div class="default">To jest domyślne</div>
	<div class="custom" style:text-box-trim={trim} style:text-box-edge={edgeStart + ' ' + edgeEnd}>
		To jest z text-box
	</div>
</section>

<style>
	form {
		display: flex;
		gap: var(--size-3);
		margin-bottom: var(--size-3);

		div {
			display: grid;
		}

		select {
			border: 1px solid black;
			padding: var(--size-1);
			width: 10rem;
		}
	}

	section {
		display: grid;
		grid-template-columns: 1fr 1fr;
		align-items: start;
		gap: min(5rem, 5vw);

		div {
			font-size: min(5rem, 5vw);
			border-block: 1px solid red;
		}
	}
</style>
