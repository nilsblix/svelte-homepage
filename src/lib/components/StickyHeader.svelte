<script>
	import { onMount } from "svelte";
	import ToggleSwitch from "./ToggleSwitch.svelte";

	import moon from "../assets/moon.svg";
	import sun from "../assets/sun.svg";

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

<div class="sticky-bar">
	<div class="content">
		<div class="left">
			<h3>Nils Blix</h3>
			<a href="https://github.com/nilsblix" target="_blank">github</a>
		</div>

		<div class="right">
			<ToggleSwitch
				onSwitch={() => toggleDarkmode()}
				left_img={sun}
				right_img={moon}
				state={dark ? 1 : 0}
			/>
		</div>
	</div>
</div>

<style>
	:global(:root) {
		--stickybar-height: 1.2rem;
	}

	.sticky-bar {
		position: fixed;
		display: flex;
		justify-content: center;
		top: 0px;
		left: 0px;
		width: calc(100vw - 2rem);

		height: var(--stickybar-height);
		margin: 0px 0px 0px 0px;
		padding: 1rem 1rem;

		z-index: 999;

		font-weight: normal;

		backdrop-filter: blur(12px);
		text-decoration: none;
		background-color: --var(page);
	}

	.content {
		display: flex;

		justify-content: space-between;
		align-items: center;
		width: max(60vw, 500px);
	}

	.left,
	.right {
		display: flex;
		gap: 1rem;
	}

	.left {
		right: 40%;
	}

	.right {
		top: 0px;
		left: 40%;
	}

	h3 {
		margin: 0 0 0 0;
	}
</style>
