<script lang="ts">
	import type { Snippet } from 'svelte';

	type Props = {
		content: Snippet;
	};
	let { content }: Props = $props();
</script>

<button
	class="explanation-btn"
	aria-label="Wyjaśnienie"
	commandfor="explanation"
	command="show-modal">?</button
>

<dialog id="explanation" closedby="any">
	<div class="header">
		<div class="title">Wyjaśnienie</div>
		<button commandfor="explanation" command="close"
			><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"
				><!-- Icon from MingCute Icon by MingCute Design - https://github.com/Richard9394/MingCute/blob/main/LICENSE --><g
					fill="none"
					fill-rule="evenodd"
					><path
						d="m12.593 23.258l-.011.002l-.071.035l-.02.004l-.014-.004l-.071-.035q-.016-.005-.024.005l-.004.01l-.017.428l.005.02l.01.013l.104.074l.015.004l.012-.004l.104-.074l.012-.016l.004-.017l-.017-.427q-.004-.016-.017-.018m.265-.113l-.013.002l-.185.093l-.01.01l-.003.011l.018.43l.005.012l.008.007l.201.093q.019.005.029-.008l.004-.014l-.034-.614q-.005-.018-.02-.022m-.715.002a.02.02 0 0 0-.027.006l-.006.014l-.034.614q.001.018.017.024l.015-.002l.201-.093l.01-.008l.004-.011l.017-.43l-.003-.012l-.01-.01z"
					/><path
						fill="currentColor"
						d="m12 14.122l5.303 5.303a1.5 1.5 0 0 0 2.122-2.122L14.12 12l5.304-5.303a1.5 1.5 0 1 0-2.122-2.121L12 9.879L6.697 4.576a1.5 1.5 0 1 0-2.122 2.12L9.88 12l-5.304 5.304a1.5 1.5 0 1 0 2.122 2.12z"
					/></g
				></svg
			></button
		>
	</div>

	<div class="content">
		{@render content()}
	</div>
</dialog>

<style>
	.explanation-btn {
		border-radius: var(--radius-round);
		border: 1px solid var(--gray-2);
		padding: var(--size-2);
		width: var(--size-8);
		height: var(--size-8);
		font-size: var(--size-5);
		font-weight: 700;
		background-color: var(--gray-9);
		color: var(--gray-2);
		transition: background-color 200ms ease;

		&:hover {
			background-color: var(--gray-8);
		}
	}

	dialog {
		width: clamp(var(--size-content-1), 100vw, 70ch);
		border: 1px solid var(--gray-2);
		border-radius: var(--radius-3);
		transition-behavior: allow-discrete;
		transition:
			translate 300ms ease,
			opacity 300ms ease;

		@starting-style {
			translate: 0 50px;
			opacity: 0;
		}

		> * {
			padding: var(--size-4);
		}

		.header {
			display: grid;
			gap: var(--size-7);
			grid-template-columns: 1fr 2rem;
			font-size: var(--size-5);
			font-weight: 700;
		}

		button {
			justify-self: end;
			align-self: start;
		}

		.content {
			text-wrap: pretty;
		}
	}
</style>
