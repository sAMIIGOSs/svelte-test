<svelte:head>
    <title>Блог</title>
</svelte:head>
<div class="container">
    <h1>Мои статьи</h1>
    <div class="blogposts">
        {#each routes as page}
        <div class="post">
            <h2>{page.title}</h2>
            <p>{page.body}</p>
            <p class="readmore">
                <a class="link" href={'/blog/posts/${page.id}'}>
                    Читать далее
                </a>
            </p>
        </div>
        {/each}
    </div>
</div>

<style>
    .container {
        margin: 50px auto;
        max-width: 800px;
        padding: 0 20px;
    }

    .blogposts{
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 20px;
    }

    .link {
        color: rgb(10, 10, 139);
    }

</style>

<script>
    import {routes} from './routes'
</script>