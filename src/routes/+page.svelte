<script>
	import StickyHeader from "$lib/components/StickyHeader.svelte";
	import Projects from "$lib/components/Projects.svelte";

	import christian from "$lib/assets/christian.png";
	import TiltingImage from "$lib/components/TiltingImage.svelte";
</script>

<StickyHeader />

<section style="width: 25%; padding: 0 0 0 0;">
	<div style="display: flex; justify-self: center; width: 100%; height: 50%;">
		<TiltingImage img_src={christian} border_radius="2em" />
	</div>
</section>

<section>
	<p>The one and only gnirf.</p>
	<Projects />
</section>

<style>
	section {
		position: relative;
		top: calc(2rem + var(--stickybar-height));
		left: 50%;

		transform: translate(-50%, 0);

		width: max(50%, 500px);
		max-width: 800px;
		padding: 1rem 0 1rem 0;

		z-index: 1;
		background: var(--page);
		border-radius: 2em;
		box-shadow: 2px 8px 18px rgba(0, 0, 0, 0.3);
		margin-bottom: 1rem;
	}

	p {
		margin-left: 3%;
	}
</style>
