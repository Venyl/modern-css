<script lang="ts">
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/mdn-css_properties_field-sizing';
</script>

<input placeholder="Mam field-sizing: content" />

<textarea placeholder="Rosne wraz z contentem i wrapuje sie do placeholdera"></textarea>

<select>
	<option>aa</option>
	<option>bbbbbbb</option>
	<option>ccccccccccccccccccc</option>
</select>

<style>
	input,
	textarea,
	select {
		outline: 1px solid black;
		field-sizing: content;
		resize: none;
	}
</style>
