<script lang="ts">
	import type { Snippet } from 'svelte';

	type Props = {
		code: Snippet;
	};

	let { code }: Props = $props();
	let codeDiv: HTMLDivElement;

	async function copyToClipboard() {
		await navigator.clipboard.writeText(codeDiv.innerText);
	}
</script>

<div class="codeblock">
	<button aria-label="Kopiuj kod do schowka" onclick={copyToClipboard}>
		<svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24"
			><!-- Icon from MingCute Icon by MingCute Design - https://github.com/Richard9394/MingCute/blob/main/LICENSE --><g
				fill="none"
				fill-rule="evenodd"
				><path
					d="m12.593 23.258l-.011.002l-.071.035l-.02.004l-.014-.004l-.071-.035q-.016-.005-.024.005l-.004.01l-.017.428l.005.02l.01.013l.104.074l.015.004l.012-.004l.104-.074l.012-.016l.004-.017l-.017-.427q-.004-.016-.017-.018m.265-.113l-.013.002l-.185.093l-.01.01l-.003.011l.018.43l.005.012l.008.007l.201.093q.019.005.029-.008l.004-.014l-.034-.614q-.005-.018-.02-.022m-.715.002a.02.02 0 0 0-.027.006l-.006.014l-.034.614q.001.018.017.024l.015-.002l.201-.093l.01-.008l.004-.011l.017-.43l-.003-.012l-.01-.01z"
				/><path
					fill="currentColor"
					d="M9 2a2 2 0 0 0-2 2v2h2V4h11v11h-2v2h2a2 2 0 0 0 2-2V4a2 2 0 0 0-2-2zM4 7a2 2 0 0 0-2 2v11a2 2 0 0 0 2 2h11a2 2 0 0 0 2-2V9a2 2 0 0 0-2-2z"
				/></g
			></svg
		>
	</button>
	<header>
		<span class="dot-1"></span><span class="dot-2"></span><span class="dot-3"></span>
	</header>
	<div class="code monospace" bind:this={codeDiv}>
		{@render code()}
	</div>
</div>

<style>
	.codeblock {
		position: relative;
		display: grid;
		grid-template-rows: var(--size-6) 1fr;
		max-width: stretch;
		max-height: 10lh;
		background-color: var(--gray-8);
		border-radius: var(--radius-3);
		overflow: clip;
		color: var(--gray-2);
		font-size: 0.875rem;

		button {
			/* display: none; */
			opacity: 0;
			top: -2rem;
			right: var(--size-3);
			position: absolute;
			background-color: var(--gray-7);
			padding: var(--size-1);
			border-radius: var(--radius-2);
			transition-property: background-color, border-color, top, opacity;
			transition-duration: 200ms;
			transition-timing-function: ease;
			border: 1px solid oklch(from var(--gray-7) calc(l * 1.1) c h);

			&:hover {
				background-color: oklch(from var(--gray-7) calc(l * 1.1) c h);
				border-color: oklch(from var(--gray-7) calc(l * 1.2) c h);
			}

			&:active {
				transition-property: background-color, top, opacity;
				border-color: var(--gray-5);
			}
		}

		&:hover button,
		button:focus-visible {
			top: var(--size-1);
			opacity: 1;
		}

		@media not (hover) {
			button {
				top: var(--size-1);
				opacity: 1;
			}
		}

		header,
		.code {
			padding: var(--size-3);
		}

		header {
			display: flex;
			align-items: center;
			gap: var(--size-3);
			background-color: var(--gray-9);
			border-bottom: 1px solid var(--gray-7);

			> span {
				display: inline-block;
				--size: 0.75rem;
				width: var(--size);
				height: var(--size);
				background-color: oklch(from var(--red-5) l c calc(h + 60 * (sibling-index() - 1)));
				border-radius: var(--radius-round);
			}
		}

		.code {
			> :global(*) {
				counter-increment: name;
			}

			> :global(*)::before {
				content: counter(name);
				margin-right: var(--size-3);
				color: var(--gray-6);
			}
		}
	}
</style>
