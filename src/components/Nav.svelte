<script>
  import { Link } from "svelte-routing";
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

  ul {
    list-style: none;
  }

  li {
    display: inline;
  }

  nav :global(a) {
    color: #fd3b1c;
  }

  nav :global(a:hover) {
    text-decoration: none;
    color: #fd3a1ca6;
  }

  .navbar-brand {
    align-items: center;
  }

  .navbar-start {
    margin-left: 0.8rem;
    padding-top: 0.7rem;
  }

  .navbar-dropdown {
    padding: 10px;
    font-size: 1rem;
  }
</style>

<nav class="navbar" role="navigation" aria-label="main navigation">
  <div class="navbar-brand">
    <Link to="/">
      <img src="images/fullLogo.png" width="142" height="38" alt="Bulma Logo" />
    </Link>

    <span
      role="button"
      class="navbar-burger burger"
      aria-label="menu"
      aria-expanded="false"
      data-target="navbarBasicExample">
      <span aria-hidden="true" />
      <span aria-hidden="true" />
      <span aria-hidden="true" />
    </span>
  </div>

  <div id="navbarBasicExample" class="navbar-menu">
    <div class="navbar-start">
      <ul>
        <li class="navbar-item">
          <Link to="/">Home</Link>
        </li>
        <li class="navbar-item">
          <Link to="/about">About</Link>
        </li>
        <li class="navbar-item has-dropdown is-hoverable">
          <Link class="navbar-link dropdown-trigger">Catagories &dtrif;</Link>
          <div class="navbar-dropdown">
            <Link to="#" class="navbar-item dropdown-item">General</Link>
            <Link to="#" class="navbar-item dropdown-item">Political</Link>
            <Link to="#" class="navbar-item dropdown-item">Comedy</Link>
            <hr class="navbar-divider" />
            <Link to="#" class="navbar-item dropdown-item">Developer</Link>
          </div>
        </li>
      </ul>
    </div>
  </div>
</nav>
