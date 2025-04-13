<script>
	export let url;
	export let name;
	export let description;
	export let span;
</script>

<a class="card" href={url} target="_blank" style={`grid-column: span ${span}`}>
	<h3>{name}</h3>
	<p>{description}</p>
</a>

<style>
	.card {
		padding: 1.5rem;
		border-radius: 1rem;
		background: rgba(255, 255, 255, 0.1);
		box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
		backdrop-filter: blur(12px);
		-webkit-backdrop-filter: blur(12px);
		border: 1px solid rgba(255, 255, 255, 0.2);
		text-decoration: none;
		color: inherit;
		transition: all 0.3s ease;
	}

	.card:hover {
		transform: translateY(-5px);
		box-shadow: 0 12px 24px rgba(0, 0, 0, 0.25);
	}

	h3 {
		margin: 0 0 0.5rem 0;
		font-size: 1.25rem;
	}

	p {
		margin: 0;
		font-size: 0.95rem;
		line-height: 1.4;
	}
</style>
