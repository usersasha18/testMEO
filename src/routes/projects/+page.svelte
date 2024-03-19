<svelte:head>
    <title>Портфолио</title>
</svelte:head>

<main class="container">
    <h1>Порфтфолио</h1>
    <div class="portfolio-list">
        {#each routes as route }
            <div class="portfolio">
                <h2>{route.title}</h2>
                <p>{route.body}</p>
                <p class="read-more">
                    <a class="link" href={`/projects/project/${route.id}`}>
                        Читать далее
                    </a>
                </p>
            </div>
        {/each}
    </div>
</main>
<script>
    import {routes} from "./routes"
</script>

<style>

    .container {
        margin: 50px auto;
        max-width: 800px;
        padding: 0 20px;
    }

    .portfolio-list {
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 20px
    }
    .portfolio {
        border: 1px solid #ddd;
        padding: 10px;
        box-shadow: 0 0 10px #eee;
    }
    .link {
        color: rgb(10, 10, 139);
    }
</style>