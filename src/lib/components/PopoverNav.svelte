<script>
	import Landing from '$lib/components/cards/Landing.svelte';
	import { fly } from 'svelte/transition';
	import { nav_expanded } from '$lib/app';
</script>

{#if $nav_expanded}
<nav class="popover" transition:fly={{ duration: 200, y: 0, x: -200 }}>
	<Landing link="/getting-started">
		<h2 slot="title">Get Started</h2>
		<p slot="blurb" class="blurb">Get Started with the FluCoMa Ecosystem</p>
	</Landing>
	<Landing link="/learn">
		<h2 slot="title">Learn</h2>
		<p slot="blurb" class="blurb">Learn how to use the FluCoMa toolkit.</p>
	</Landing>

	<Landing link="/explore">
		<h2 slot="title">Explore</h2>
		<p slot="blurb" class="blurb">Explore what other people are doing.</p>
	</Landing>

	<Landing link="/reference">
		<h2 slot="title">References</h2>
		<p slot="blurb" class="blurb">References for all the toolkit algorithms.</p>
	</Landing>

	<p class="acknowledgements">
		The development of Learn is led by <a href="https://jamesbradbury.net">James Bradbury</a>,
		<a href="https://jacob-hart.com">Jacob Hart</a>
		and <a href="https://www.tedmooremusic.com">Ted Moore</a>.
	</p>
</nav>
{/if}

<style>
	.popover {
		opacity: 1;
		display: flex;
		flex-direction: column;
		gap: 0.5em;
		position: fixed;
		top: 55px;
		left: 0;
		background-color: white;
		opacity: 1;
		width: min(400px, 50%);
		height: 100vh;
		text-align: left;
		padding: 1em 2em;
		z-index: 99;
	}

	.blurb {
		color: var(--grey);
		text-align: left;
	}

	.acknowledgements {
		margin-top: 1em;
		font-size: 0.9rem;
	}
</style>
