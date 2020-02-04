<script>
  import { Link } from 'svelte-routing'
  import { onMount } from 'svelte'

  onMount(() => {
    const navbarBurgers = Array.prototype.slice.call(
      document.querySelectorAll('.navbar-burger'),
      0,
    )

    if (navbarBurgers.length > 0) {
      navbarBurgers.forEach(el => {
        const target = el.dataset.target
        const target2 = document.getElementById(target)

        el.classList.toggle('is-active')
        target2.classList.toggle('is-active')
      })
    }
  })
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
    padding: 15px;
    font-size: 1rem;
  }

  .navbar-dropdown :global(a) {
    padding: 18px;
  }

  .d-link {
    padding-left: 8px !important;
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
          <Link>Catagories &dtrif;</Link>
          <div class="navbar-dropdown">
            <Link to="#">
              <span class="d-link">General</span>
            </Link>
            <Link to="#">
              <span class="d-link">Political</span>
            </Link>
            <Link to="#">
              <span class="d-link">Comedy</span>
            </Link>
            <hr class="navbar-divider" />
            <Link to="#">
              <span class="d-link">Developer</span>
            </Link>
          </div>
        </li>
      </ul>
    </div>
    <div class="navbar-end">
      <div class="navbar-item">
        <div class="buttons">
          <button id="sign-up-button" class="button is-primary">
            <strong>Sign up</strong>
          </button>
          <button id="login-button" class="button is-dark">Log in</button>
        </div>
      </div>
    </div>
  </div>
</nav>
