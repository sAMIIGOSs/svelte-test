<nav>
    <div class="nav-container">
        <a href="/" class="nav-logo" title="Back to Homepage">Имя Фамилия</a>
        <div class="nav-links">
            <!-- svelte-ignore missing-declaration -->
            {#if link.inShow}
            <!-- svelte-ignore missing-declaration -->
            <a href={link.href} class="link">{link.title}</a>
            {/if}
        </div>
    </div>
</nav>

<div class="container">
   <!--Pages will be injacted below-->
   <slot></slot>
</div>

<script>
    const nav = [
        {
            title: 'Обо мне',
            href: '/about',
            isShow: true,
        },
        {
            title: 'Блог',
            href: '/blog',
            isShow: true,
        },
        {
            title: 'Портфолио',
            href: '/project',
            isShow: true,
        },
        {
            title: 'Контакты',
            href: '/contact',
            isShow: true,
        },
        {
            title: 'temp',
            href: '/temp',
            isShow: false,
        }
    ]
</script>

<style>
    .container {
        max-width: 1400px;
        margin: 50px auto;
    }
</style>