<script>
	import { onMount } from "svelte";

	let dark = false;

	const applyTheme = () => {
		document.documentElement.dataset.theme = dark ? "dark" : "light";
	};

	const toggleDarkmode = () => {
		dark = !dark;
		applyTheme();
	};

	onMount(() => {
		applyTheme();
	});
</script>

<header>
	<h1>Nils, Motherfucking, Blix.</h1>
	<h3>The original gnirf.</h3>
	<button on:click={toggleDarkmode}>Toggle theme</button>
</header>

<style>
	header {
		margin-top: 2rem;
		text-align: center;
	}

	h3 {
		font-weight: normal;
	}
</style>
