<script>
  import { onMount } from "svelte";

  onMount(() => {
    const navbarBurgers = Array.prototype.slice.call(
      document.querySelectorAll(".navbar-burger"),
      0
    );

    if (navbarBurgers.length > 0) {
      navbarBurgers.forEach(el => {
        const target = el.dataset.target;
        const target2 = document.getElementById(target);

        el.classList.toggle("is-active");
        target2.classList.toggle("is-active");
      });
    }
  });
</script>

<style>
  nav {
    border-bottom: 1px solid rgba(255, 62, 0, 0.1);
    padding: 0 1em;
  }
</style>

<nav class="navbar" role="navigation" aria-label="main navigation">
  <div class="navbar-brand">
    <a class="navbar-item" href="https://bulma.io">
      <img
        src="https://bulma.io/images/bulma-logo.png"
        alt="Bulma: Free, open source, and modern CSS framework based on Flexbox"
        width="112"
        height="28" />
    </a>

    <span
      role="button"
      class="navbar-burger"
      aria-label="menu"
      aria-expanded="false">
      <span aria-hidden="true" />
      <span aria-hidden="true" />
      <span aria-hidden="true" />
    </span>
  </div>
</nav>
