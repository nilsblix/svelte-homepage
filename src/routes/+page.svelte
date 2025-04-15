<script>
	import Header from "../lib/components/Header.svelte";
	import Projects from "../lib/components/Projects.svelte";
	import TiltingImage from "$lib/components/TiltingImage.svelte";
</script>

<section>
	<Header />
	<a href="https://github.com/nilsblix" target="_blank">github</a>
	<Projects />
</section>

<style>
	section {
		position: absolute;
		top: 0;
		left: 50%;

		transform: translate(-50%, 0);

		width: max(50%, 500px);
		max-width: 800px;
		/* height: 100vh; */
		padding-bottom: 1rem;

		z-index: -1;
		background: var(--page);
		border-radius: 2em;
		box-shadow: 2px 8px 18px rgba(0, 0, 0, 0.3);
	}

	a {
		color: var(--secondary);
		margin-left: 3%;
	}
</style>
