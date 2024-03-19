<svelte:head>
  <title>Феофанов Александр</title>
</svelte:head>

<div class="container">
    <nav>
        <div class="nav-container">
          <a href="/">Феофанов Александр</a>
          <div class="nav-links">
            {#each nav as link }
                {#if link.isShow}
                    <a class="link" href={link.href}>{link.title}</a>     
                {/if}           
            {/each}
          </div>
        </div>
      </nav>
    <slot />
</div>

<script>
    const nav = [
        {
            title: "Обо мне",
            href: "/about",
            isShow: true
        },
        {
            title: "Блог",
            href: "/blog",
            isShow: true
        },
        {
            title: "Порфолио",
            href: "/projects",
            isShow: true
        },
        {
            title: "Контакты",
            href: "/contact",
            isShow: true
        },
    ]
</script>

<style>

    .nav-container {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
    }
    .container {
        max-width: 1400px;
        margin: 0 auto;;
    }
    .link {
        margin-right: 2rem;
    }
</style>
