<script>
    export let url;
    export let name;
    export let description;
</script>

<a class="card" href={url} target="_blank">
    <h3>{name}</h3>
    <p>{description}</p>
</a>

<style>
    .card {
        padding: 1.5rem;
        border-radius: 1rem;
        background: var(--card-bg);
        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        text-decoration: none;
        color: inherit;
        transition: all 0.3s ease;

        /* border: 1px solid red; */
    }

    .card:hover {
        transform: translateY(-5px);
    }
</style>
