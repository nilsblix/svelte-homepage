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
		<div class="image-stack">
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
			<img
				src={images[selected]}
				alt=""
				style={`width: calc(100% - ${images.length > 1 ? "1rem" : "0px"}`}
			/>
		</div>
	{/if}
</div>

<style>
	:global(.project-block) {
		display: flex;
		flex-direction: column;
		gap: 1rem;
		padding: 0.5rem;
		background-color: var(--block-bg);
		border-radius: 1.4rem;
		align-self: start;
		border: 1px solid rgba(255, 255, 255, 0.1);
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
		margin-top: 0;
		border-radius: 1rem;
	}

	.selectors {
		display: flex;
		flex-direction: column;
		margin-bottom: 0.5rem;
		margin-right: 0.5rem;
		gap: 0.8rem;
	}

	.selectors button {
		background-color: var(--inactive-widget);
		border: var(--inactive-widget);
		width: 0.5rem;
		height: 4rem;
		padding: 0;
	}

	.selectors button:hover {
		background-color: var(--tertiary);
	}

	.selectors button.selected {
		background-color: var(--active-widget);
		border: var(--active-widget);
	}
</style>
