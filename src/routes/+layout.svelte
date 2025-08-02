<script lang="ts">
	import { browserAvailability } from '$lib/stores.svelte';
	import '$lib/styles/index.css';
	const { children } = $props();
</script>

<div class="wrapper">
	<header>
		<a href="/"> Strona główna </a>
		<div class="v-rule" style:display={browserAvailability.href ? 'block' : 'none'}></div>
		<a
			target="_blank"
			href={browserAvailability.href}
			style:display={browserAvailability.href ? 'flex' : 'none'}
		>
			Dostępność
		</a>
	</header>

	<main>
		{@render children()}
	</main>
</div>

<style>
	.wrapper {
		display: grid;
		grid-template-rows: auto 1fr;
	}

	header {
		display: flex;
		gap: var(--size-4);
		align-items: center;
		padding: var(--size-4) var(--size-7);
		border-bottom: 1px solid var(--gray-2);

		a {
			display: flex;
			align-items: center;
			gap: var(--size-1);
			color: var(--gray-9);
			text-decoration-color: transparent;
			text-underline-offset: 0.0625rem;
			transition:
				text-decoration-color 200ms ease,
				text-underline-offset 200ms ease;

			&:hover {
				text-decoration-color: currentColor;
				text-underline-offset: 0.125rem;
			}
		}
	}

	main {
		width: min(1440px, calc(100vw - 2rem));
		margin: var(--size-10) auto;
	}
</style>
