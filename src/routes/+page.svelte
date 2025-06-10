<script lang="ts">
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = '';
</script>

<h1>Modern CSS</h1>

<h2>Popovery i Modale</h2>
<ul>
	<li><a href="/popover">[popover], [popovertarget]</a></li>
	<li><a href="/">[interesttarget], interest-target-delay, :has-interest, [popover="hint"]</a></li>
	<li>
		<a href="/"
			>appearance: base-select, &lt;selectedcontent&gt;, ::picker(), ::picker-icon, ::checkmark,
		</a>
	</li>
	<li>
		<a href="/">&lt;hr&gt; in &lt;select&gt;</a>
	</li>
	<li><a href="/">[closedby]</a></li>
	<li><a href="/">[command], [commandfor]</a></li>
</ul>

<h2>Anchor API</h2>
<ul>
	<li><a href="/">anchor-name, position-anchor, anchor(), position-area</a></li>
	<li><a href="/">@position-try, position-try-fallbacks, position-try-order</a></li>
</ul>

<h2>Scrollowanie</h2>
<ul>
	<li><a href="/">overflow: clip</a></li>
	<li><a href="/">overscroll-behavior</a></li>
	<li><a href="/">scroll-margin</a></li>
	<li><a href="/">scroll-snap</a></li>
	<li><a href="/">scrollbar-width</a></li>
	<li><a href="/">view(), scroll()</a></li>
	<li><a href="/">::scroll-button, ::scroll-marker, ::scroll-marker-group, :target-current</a></li>
	<li><a href="/">scroll-state()</a></li>
</ul>

<h2>Kolory</h2>
<ul>
	<li><a href="/">accent-color</a></li>
	<li><a href="/">caret-color</a></li>
	<li><a href="/">Relative colors</a></li>
	<li><a href="/">color-mix()</a></li>
	<li><a href="/">color()</a></li>
</ul>

<h2>Przejścia</h2>
<ul>
	<li><a href="/">linear()</a></li>
	<li><a href="/">interpolate-size</a></li>
	<li><a href="/">@starting-style, transition-behavior</a></li>
	<li><a href="/">@view-transition, navigation, view-transition-name</a></li>
</ul>

<h2>Inne</h2>
<ul>
	<li><a href="/media-hover">@media (hover)</a></li>
	<li><a href="/media-range-syntax">Media query range syntax</a></li>
	<li><a href="/">paint-order</a></li>
	<li><a href="/">fit-content()</a></li>
	<li><a href="/">border-image</a></li>
	<li><a href="/">any-link</a></li>
	<li><a href="/">:has()</a></li>
	<li><a href="/">interactivity: inert</a></li>
	<li><a href="/">@layer</a></li>
	<li><a href="/">@property</a></li>
	<li><a href="/">Multi-value display</a></li>
	<li><a href="/">named &lt;details&gt;, ::details-content</a></li>
	<li><a href="/">calc-size()</a></li>
	<li><a href="/">field-sizing</a></li>
	<li><a href="/">container-name, container-type, @container, style()</a></li>
	<li><a href="/">typed attr()</a></li>
	<li><a href="/">sibling-count(), sibling-index()</a></li>
	<li><a href="/">progress()</a></li>
	<li><a href="/">width / height: stretch</a></li>
	<li><a href="/">@function</a></li>
	<li><a href="/">if()</a></li>
	<li><a href="/">shape()</a></li>
	<li><a href="/">text-box</a></li>
	<li><a href="/">box-decoration-break</a></li>
	<li><a href="/">animation-composition</a></li>
</ul>

<style>
	h1 {
		font-size: var(--size-10);
		font-weight: 700;
		text-align: center;
		margin-bottom: var(--size-10);
	}

	h2 {
		font-size: var(--size-7);
		font-weight: 700;
		text-align: center;
		margin-bottom: var(--size-4);

		&:not(:first-of-type) {
			margin-top: var(--size-7);
		}
	}

	ul {
		display: grid;
		gap: var(--size-4);
		place-content: center;
		grid-template-columns: repeat(
			auto-fit,
			minmax(min(var(--size-content-1), 100%), var(--size-content-2))
		);
	}

	li {
		text-align: center;

		a {
			display: grid;
			place-items: center;
			height: 100%;
			background-color: #fafafa;
			border-radius: var(--radius-3);
			padding: var(--size-2) var(--size-4);
			min-height: calc(2lh + 2 * var(--size-2));
			border: 1px solid #dfdfdf;
			transition-property: border, box-shadow;
			transition-duration: 200ms;
			transition-timing-function: ease;
			color: var(--gray-9);
			text-decoration: none;

			&:hover {
				border: 1px solid #bbb;
				box-shadow: 1px 1px 8px -6px #aaa;
			}

			&[href='/'] {
				pointer-events: none;
				opacity: 0.75;
				position: relative;

				&::before {
					content: '✕';
					position: absolute;
					top: -0.75rem;
					left: -0.375rem;
					color: var(--red-5);
					font-size: var(--size-5);
					font-weight: 700;
				}
			}
		}
	}
</style>
