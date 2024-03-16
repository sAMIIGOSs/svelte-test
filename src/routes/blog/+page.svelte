

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
                <a class="link" href={/blog/posts/${page.id}}>
                    Читать далее
                </a>
            </p>
        </div>
        {/each}
    </div>
</div>


<script>
    import {routes} from './routes'
</script>