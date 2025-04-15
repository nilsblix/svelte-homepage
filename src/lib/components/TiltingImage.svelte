<script>
	export let img_src;
	let rx = 0;
	let ry = 0;

	// @ts-ignore
	const handleMouseMove = (e) => {
		const rect = e.currentTarget.getBoundingClientRect();
		const centerX = rect.width / 2;
		const centerY = rect.height / 2;
		const offsetX = e.clientX - rect.left;
		const offsetY = e.clientY - rect.top;

		// Map the position to a rotation range
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
	aria-label={``}
>
	<img src={img_src} alt="Cool beans?" style:transform={`rotateY(${rx}deg) rotateX(${ry}deg)`} />
</div>

<style>
	div {
		display: flex;
		justify-content: center;
		perspective: 1300px;
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
