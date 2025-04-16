<script>
	export let onSwitch;
	export let left_img;
	export let right_img;
	export let state = 0; // 0 is left, 1 is right

	const onclick = () => {
		onSwitch();
	};
</script>

<button
	on:click={() => onclick()}
	style={`background: var(--${state == 0 ? "tertiary" : "block-bg"});`}
>
	<div class="imgs">
		<div class={`icon-wrapper ${state == 0 ? "selected" : ""}`}>
			<img src={left_img} alt="" style={`${state == 1 ? "filter: invert(1);" : ""}`} />
		</div>
		<div class={`icon-wrapper ${state == 1 ? "selected" : ""}`}>
			<img src={right_img} alt="" />
		</div>
	</div>
</button>

<style>
	button {
		padding: 0 8px 0 8px;
		border-radius: 2rem;
	}

	.imgs {
		border: 1px solid green;
		display: flex;
		gap: 1.5rem;
		border-radius: 1.5rem;
		width: 100%;
	}

	.icon-wrapper img {
		width: 24px;
		height: 24px;
	}

	.icon-wrapper {
		border: 1px solid pink;
		display: flex;
		align-items: center;
	}

	.selected {
		background-color: var(--white);
		--size: 32px;
		border-radius: var(--size);
		width: var(--size);
		height: var(--size);
	}
</style>
