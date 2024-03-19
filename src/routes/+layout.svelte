<svelte:head>
  <title>Феофанов Александр</title>
</svelte:head>

<div class="container">
    <nav>
        <div class="nav-container">
          <a href="/">Феофанов Александр</a>
          <div class="nav-links">
            {#each nav as link }
                <a class="link" href={link.href}>{link.title}</a>                
            {/each}
          </div>
        </div>
      </nav>
    <slot />
</div>

<script>
  import { NavbarCollapse } from "react-bootstrap";

    const nav = [
        {
            title: "Обо мне",
            href: "/about"
        },
        {
            title: "Блог",
            href: "/blog"
        },
        {
            title: "Порфолио",
            href: "/projects"
        },
        {
            title: "Контакты",
            href: "/contact"
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
