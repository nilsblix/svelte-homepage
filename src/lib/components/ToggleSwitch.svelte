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
	style={`
        background: var(--${state == 0 ? "tertiary" : "card-bg"});
        border: 1px solid var(--${state == 0 ? "tertiary" : "card-bg"});
    `}
>
	<div class={`icon-wrapper ${state == 0 ? "selected" : ""}`}>
		<img src={left_img} alt="" style={`${state == 1 ? "filter: invert(1);" : ""}`} />
	</div>
	<div class={`icon-wrapper ${state == 1 ? "selected" : ""}`}>
		<img src={right_img} alt="" />
	</div>
</button>

<style>
	button {
		padding: 0 0 0 0;
		border-radius: 1.5rem;
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 2px;
	}

	.icon-wrapper img {
		--size: 20px;
		width: var(--size);
		height: var(--size);
		transition: all 0.3s ease;
	}

	.icon-wrapper {
		display: flex;
		justify-content: center;
		align-items: center;

		border-radius: 1.5rem;
		height: 36px;
		width: 36px;
	}

	.selected {
		background-color: var(--white);
	}
</style>
