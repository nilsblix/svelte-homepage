<script>
	import ProjectCard from "./ProjectCard.svelte";

	export let project;
	// @ts-ignore
	export let images = [];

	let selected = 0;
</script>

<div class="project-block" style:grid-column={`span ${project.span || 1}`}>
	<ProjectCard {...project} />
	{#if images.length}
		{#if images.length > 1}
			<div class="selectors">
				{#each images as _, i}
					<button
						class:selected={selected == i}
						on:click={() => {
							selected = i;
						}}
						aria-label={`${i}`}
					></button>
				{/each}
			</div>
		{/if}
		<div class="image-stack">
			<img src={images[selected]} alt="" />
		</div>
	{/if}
</div>

<style>
	.project-block {
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}

	.image-stack {
		display: flex;
		justify-content: center;
		perspective: 1300px;
		width: 100%;

		margin-left: auto;
		margin-right: auto;
	}

	img {
		border-radius: 1rem;
		width: 100%;
	}

	.selectors {
		display: flex;
		margin-bottom: 0.5rem;
		justify-content: center;
		gap: 0.8rem;
	}

	.selectors button {
		background-color: var(--inactive-widget);
		border: var(--inactive-widget);
		height: 0.5rem;
		padding: 0;
		width: 4rem;
	}

	.selectors button.selected {
		background-color: var(--active-widget);
		border: var(--active-widget);
	}
</style>
