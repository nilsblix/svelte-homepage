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
		<img
			class={state == 0 ? "selected" : ""}
			src={left_img}
			alt=""
			style={`${state == 1 ? "filter: invert(1);" : ""}`}
		/>
		<img class={state == 1 ? "selected" : ""} src={right_img} alt="" />
	</div>
	<!-- <span class="toggle" style={`left: ${state == 0 ? "1rem" : "3rem"};`}></span> -->
</button>

<style>
	button {
		border: 1px solid red;
	}

	.imgs {
		border: 1px solid green;
		display: flex;
		gap: 1rem;
		border-radius: 1.5rem;
	}

	/* .toggle { */
	/* 	background-color: var(--white); */
	/* 	--size: 1.1rem; */
	/* 	width: var(--size); */
	/* 	height: var(--size); */
	/* } */

	img {
		width: 16px;
	}

	img .selected {
		background-color: var(--white);
	}
</style>
