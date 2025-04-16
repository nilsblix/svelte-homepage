<script>
	export let img_src;
	export let border_radius = "1rem";
	let rx = 0;
	let ry = 0;

	// @ts-ignore
	const handleMouseMove = (e) => {
		const rect = e.currentTarget.getBoundingClientRect();
		const centerX = rect.width / 2;
		const centerY = rect.height / 2;
		const offsetX = e.clientX - rect.left;
		const offsetY = e.clientY - rect.top;

		rx = ((offsetX - centerX) / centerX) * 10; // left-right
		ry = -((offsetY - centerY) / centerY) * 10; // up-down
	};

	const resetRotation = () => {
		rx = 0;
		ry = 0;
	};
</script>

<div
	on:mousemove={(e) => handleMouseMove(e)}
	on:mouseleave={() => {
		resetRotation();
	}}
>
	<!-- <img src={img_src} alt="" style:transform={`rotateY(${rx}deg) rotateX(${ry}deg)`} /> -->
	<img
		src={img_src}
		alt=""
		style={`
        transform: rotateY(${rx}deg) rotateX(${ry}deg);
        border-radius: ${border_radius};
    `}
	/>
</div>

<style>
	div {
		display: flex;
		justify-content: center;
		perspective: 1000px;
		width: 100%;

		margin-left: auto;
		margin-right: auto;
	}

	img {
		border-radius: 1rem;
		transition: transform 0.1s ease;
		width: 100%;
	}
</style>
