<script lang="ts">
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/mdn-html_elements_hr_hr_in_select';
</script>

<select>
	<option>A</option>
	<option>B</option>
	<hr />
	<option>C</option>
	<option>D</option>
</select>
