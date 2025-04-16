<script>
	import StickyHeader from "$lib/components/StickyHeader.svelte";
	import Projects from "../lib/components/Projects.svelte";
</script>

<StickyHeader />
<section>
	<p>The one and only gnirf.</p>
	<Projects />
</section>

<style>
	section {
		position: absolute;
		top: calc(2rem + var(--stickybar-height));
		left: 50%;

		transform: translate(-50%, 0);

		width: max(50%, 500px);
		max-width: 800px;
		padding-bottom: 1rem;

		z-index: -1;
		background: var(--page);
		border-radius: 2em;
		box-shadow: 2px 8px 18px rgba(0, 0, 0, 0.3);
	}

	p {
		margin-left: 3%;
	}
</style>
