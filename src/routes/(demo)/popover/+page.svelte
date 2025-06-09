<script lang="ts">
	import Explanation from '$lib/components/Explanation.svelte';
	import { browserAvailability } from '$lib/stores.svelte';

	browserAvailability.href = 'https://caniuse.com/mdn-api_htmlelement_popover';
</script>

<Explanation>
	{#snippet content()}
		Przycisk "Otwórz popover" zawiera atrybut <code>popovertarget="my-popover"</code>.
		<br /><br />
		Na stronie znajduje się
		<code> &lt;div id="my-popover" popover&gt;Siema&lt;div&gt; </code>, który dzięki atrybutowi
		<code>popover</code>
		domyślnie ma <code>display: none</code>, lecz po kliknięciu przycisku dostaje
		<code>display: block</code>.
		<br /><br />
		Atrybut <code>popover</code> domyślnie jest konwertowany na <code>popover="auto"</code>, co
		pozwala nam zamykać popovery light-dismissem (klikajać poza ich obszar). Innymi możliwymi
		wartościami są
		<a href="/popover-hint"><code>hint</code></a>, a także
		<code>manual</code>.
		<br /><br />
		Wartość <code>auto</code> w zamian za funkcjonalność light-dismiss nie pozwala nam tworzyć wiele
		popoverów jednocześnie, do tego potrzebujemy użyć wartość <code>manual</code>, która natomiast
		nie posiada light-dismissa.
		<br /><br />
		Popovery domyślnie pozycjonowane są na środku ekranu i istnieją we własnym
		<code>#top-layer</code>.
	{/snippet}
</Explanation>
<button class="btn" popovertarget="my-popover">Otwórz popover</button>
<div class="popover" id="my-popover" popover="auto">Siema</div>

<style>
	.popover {
		border: 1px solid var(--gray-2);
		padding: var(--size-2);
		border-radius: var(--radius-3);
	}
</style>
