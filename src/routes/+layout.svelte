<script lang="ts">
	import { browserAvailability } from '$lib/stores.svelte';
	import '$lib/styles/index.css';
	const { children } = $props();
</script>

<div class="wrapper">
	<header>
		<a href="/" class="home">
			<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24"
				><!-- Icon from MingCute Icon by MingCute Design - https://github.com/Richard9394/MingCute/blob/main/LICENSE --><g
					fill="none"
					><path
						d="m12.593 23.258l-.011.002l-.071.035l-.02.004l-.014-.004l-.071-.035q-.016-.005-.024.005l-.004.01l-.017.428l.005.02l.01.013l.104.074l.015.004l.012-.004l.104-.074l.012-.016l.004-.017l-.017-.427q-.004-.016-.017-.018m.265-.113l-.013.002l-.185.093l-.01.01l-.003.011l.018.43l.005.012l.008.007l.201.093q.019.005.029-.008l.004-.014l-.034-.614q-.005-.018-.02-.022m-.715.002a.02.02 0 0 0-.027.006l-.006.014l-.034.614q.001.018.017.024l.015-.002l.201-.093l.01-.008l.004-.011l.017-.43l-.003-.012l-.01-.01z"
					/><path
						fill="currentColor"
						d="M13.228 2.688a2 2 0 0 0-2.456 0l-8.384 6.52C1.636 9.795 2.05 11 3.003 11H4v8a2 2 0 0 0 2 2h4v-6a2 2 0 1 1 4 0v6h4a2 2 0 0 0 2-2v-8h.997c.952 0 1.368-1.205.615-1.791z"
					/></g
				></svg
			>
			Strona główna
		</a>

		<a
			class="availability"
			target="_blank"
			href={browserAvailability.href}
			style:display={browserAvailability.href ? 'flex' : 'none'}
		>
			<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24"
				><!-- Icon from MingCute Icon by MingCute Design - https://github.com/Richard9394/MingCute/blob/main/LICENSE --><g
					fill="none"
					fill-rule="evenodd"
					><path
						d="m12.594 23.258l-.012.002l-.071.035l-.02.004l-.014-.004l-.071-.036q-.016-.004-.024.006l-.004.01l-.017.428l.005.02l.01.013l.104.074l.015.004l.012-.004l.104-.074l.012-.016l.004-.017l-.017-.427q-.004-.016-.016-.018m.264-.113l-.014.002l-.184.093l-.01.01l-.003.011l.018.43l.005.012l.008.008l.201.092q.019.005.029-.008l.004-.014l-.034-.614q-.005-.019-.02-.022m-.715.002a.02.02 0 0 0-.027.006l-.006.014l-.034.614q.001.018.017.024l.015-.002l.201-.093l.01-.008l.003-.011l.018-.43l-.003-.012l-.01-.01z"
					/><path
						fill="currentColor"
						d="M12 2c5.523 0 10 4.477 10 10s-4.477 10-10 10S2 17.523 2 12S6.477 2 12 2m1.482 14.94a18 18 0 0 1-2.964 0q.14.596.31 1.102c.251.755.53 1.293.79 1.622c.127.162.23.248.3.29l.051.028l.03.008l.032-.008l.051-.027a1.2 1.2 0 0 0 .3-.29c.26-.33.539-.868.79-1.623q.17-.506.31-1.102m-8.675-1.435a8.03 8.03 0 0 0 4.441 4.01a11 11 0 0 1-.318-.84a16 16 0 0 1-.52-2.033a18 18 0 0 1-3.603-1.137m14.387 0c-1.145.5-2.351.883-3.605 1.137a16 16 0 0 1-.52 2.034q-.144.437-.318.838a8.03 8.03 0 0 0 4.443-4.01Zm-5.218-4.634a15 15 0 0 1-3.952 0a26 26 0 0 0 .141 4.025a16.2 16.2 0 0 0 3.67 0A25 25 0 0 0 14 12q0-.576-.024-1.13ZM4.568 9.032a8 8 0 0 0-.52 3.856a16 16 0 0 0 4.067 1.637a28 28 0 0 1-.074-4.053a15 15 0 0 1-3.473-1.44m14.864 0a15 15 0 0 1-3.473 1.44a28 28 0 0 1-.074 4.053a16 16 0 0 0 4.066-1.637a8 8 0 0 0-.52-3.855Zm-7.416-5.02l-.011-.002l-.02.003l-.038.015a1.2 1.2 0 0 0-.33.307c-.26.33-.538.868-.79 1.622c-.27.808-.488 1.8-.633 2.919a13 13 0 0 0 3.612 0c-.145-1.12-.364-2.111-.633-2.919c-.252-.754-.53-1.293-.79-1.622a1.2 1.2 0 0 0-.3-.29l-.067-.032Zm-2.768.474a8 8 0 0 0-3.71 2.797c.843.484 1.746.876 2.695 1.163c.16-1.164.397-2.223.697-3.122q.145-.438.318-.838m5.504 0q.172.4.318.838c.3.9.537 1.958.697 3.122a13 13 0 0 0 2.695-1.163a8 8 0 0 0-3.71-2.797"
					/></g
				></svg
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
		align-items: center;
		padding: var(--size-4) var(--size-7);
		border-bottom: 1px solid var(--gray-2);

		a {
			color: var(--gray-9);
			text-decoration: none;
			text-decoration-color: transparent;
			transition: text-decoration-color 200ms ease;

			&:hover {
				text-decoration: underline;
				text-decoration-color: currentColor;
			}
		}
	}

	.home,
	.availability {
		display: flex;
		align-items: center;
		gap: var(--size-1);
	}

	.availability {
		margin-left: auto;
	}

	main {
		width: min(1440px, calc(100vw - 2rem));
		margin: var(--size-10) auto;
	}
</style>
