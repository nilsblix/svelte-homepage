<script>
	import ProjectBlock from "./ProjectBlock.svelte";

	import christian from "../assets/christian.png";
	import nvim_png from "../assets/nvim.png";
	import nix_png from "../assets/nix.png";
	// import TiltingImage from "./TiltingImage.svelte";

	const projects = {
		xpbd: {
			url: "https://nilsblix.github.io/xpbd-v2/",
			name: "xpbd-v2",
			description:
				"A 2d physics engine using the XPBD method (2020). It solves constraints locally and  iteratively to hopefully approach the global solution. It does not support collisions.",
			span: 1,
		},
		nvb_imgui: {
			url: "https://nilsblix.github.io/nvb-imgui/dist",
			name: "nvb-imgui",
			description:
				"A typescript-based immediate-mode gui, designed for myself primarily. It is used in _neural_ to handle the gui.",
			span: 1,
		},
		nvb_zigics: {
			url: "https://github.com/nilsblix/nvb-zigics",
			name: "nvb-zigics",
			description:
				"A universal zig-based physics engine based on Sequential Impulses by Erin Catto. It features a constraint and a collision solver. It is currently unfinished but creating WASM-bindings is on the todo-list.",
			span: 2,
		},
		neural: {
			url: "https://nilsblix.github.io/neural/dist",
			name: "neural",
			description:
				"A neural-network testbench for building, comparing and testing NNs on the MNIST dataset.",
			span: 1,
		},
		nix_config: {
			url: "https://github.com/nilsblix/nix-config",
			name: "nix-config",
			description:
				"Not really a project, per se, but it did consume quite a bit of my time. Fighting homebrew is what led to my frequent system wipes.",
			span: 1,
		},
	};
</script>

<div class="projects">
	<ProjectBlock project={projects.xpbd} images={[christian]} />
	<ProjectBlock project={projects.nvb_imgui} images={[christian, nvim_png]} />
	<ProjectBlock project={projects.nvb_zigics} images={[christian, nvim_png, nix_png]} />
	<ProjectBlock project={projects.neural} />
	<ProjectBlock project={projects.nix_config} />
</div>

<style>
	.projects {
		padding-left: 1rem;
		padding-right: 1rem;

		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
		gap: 2rem;
		margin-top: 2rem;
	}
</style>
