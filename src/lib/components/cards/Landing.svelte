<script>
	import ArrowRight from '$lib/components/ArrowRight.svelte';
	import { nav_expanded } from '$lib/app';
	export let link = '/';
</script>

<div class="container">
	<slot name="title" />
	<slot name="blurb" />
	<a
		on:click={() => {
			$nav_expanded = false;
		}}
		class="linkout"
		href={link}>Learn More <ArrowRight /></a
	>
</div>

<style>
	.container {
		margin-top: 0.5em;
		margin-bottom: 0.5em;
	}

	.container > :global(h2) {
		margin: 0;
	}

	.linkout {
		display: grid;
		grid-template-columns: auto auto;
		justify-content: left;
		place-items: center;
		gap: 0.2em;
	}

	.linkout:hover {
		background-color: transparent;
		color: var(--med-blue);
		gap: 0.3em;
	}

	.linkout,
	.linkout:hover {
		transition: gap 80ms ease-in-out;
	}
</style>
