<script>
	import Header from '../lib/components/Header.svelte';
	import ProjectCard from '../lib/components/ProjectCard.svelte';

	const projects = [
		{
			url: 'https://nilsblix.github.io/xpbd-v2/',
			name: 'xpbd-v2',
			description:
				'A 2d physics engine using the XPBD method (2020). It solves constraints locally and  iteratively to hopefully approach the global solution. It does not support collisions.'
		},
		{
			url: 'https://nilsblix.github.io/nvb-imgui/dist',
			name: 'nvb-imgui',
			description:
				'A typescript-based immediate-mode gui, designed for myself primarily. It is used in ´neural´ to handle the gui.'
		},
		{
			url: 'https://nilsblix.github.io/neural/dist',
			name: 'neural',
			description:
				'A neural-network testbench for building, comparing and testing NNs on the MNIST dataset.'
		},
		{
			url: 'https://github.com/nilsblix/nix-config',
			name: 'nix-config',
			description:
				'Not really a project, per se, but it did consume quite a bit of my time. Fighting homebrew is what lead to my frequent system wipes.'
		}
	];
</script>

<section>
	<Header />
	<a href="https://github.com/nilsblix" target="_blank">github</a>
	<div class="projects">
		{#each projects as project}
			<ProjectCard {...project} />
		{/each}
	</div>
</section>

<style>
	section {
		position: absolute;
		top: 0;
		left: 50%;

		transform: translate(-50%, 0);

		width: max(50%, 500px);
		max-width: 900px;
		height: 100vh;

		z-index: -1;
		background: var(--page);
		border-radius: 2em;
		box-shadow: 2px 8px 18px rgba(0, 0, 0, 0.3);
	}

	section > :not(.projects) {
		margin-left: 3%;
	}

	.projects {
		padding-left: 1rem;
		padding-right: 1rem;

		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
		gap: 2rem;
		margin-top: 1rem;
	}

	a {
		color: var(--secondary);
	}
</style>
