<script>
  import { Link } from 'svelte-routing'
  import { onMount } from 'svelte'

  onMount(() => {
    const burger = document.querySelector('.burger')
    const nav = document.querySelector('#' + burger.dataset.target)

    burger.addEventListener('click', function() {
      burger.classList.toggle('is-active')
      nav.classList.toggle('is-active')
    })
  })
</script>

<style>
  nav {
    border-bottom: 1px solid rgba(255, 62, 0, 0.1);
    padding: 0 1em;
    margin-top: 12px;
  }

  ul {
    list-style: none;
  }

  li {
    display: inline;
  }

  nav :global(a) {
    color: #9624c4;
  }

  nav :global(a:hover) {
    text-decoration: none;
    color: #ccb20c;
  }

  .is-project-primary {
    background-color: #9624c4;
    border: 1px solid transparent;
    color: #fff;
    font-size: 1rem;
    font-weight: normal;
  }

  .is-project-primary:hover {
    background-color: #712391e1;
    border: 1px solid transparent;
    color: #fff;
    font-size: 1rem;
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

  .navbar-dropdown :global(a) {
    padding: 6px;
  }

  .d-link {
    padding-left: 8px !important;
  }
</style>

<nav class="navbar" role="navigation" aria-label="main navigation">
  <div class="navbar-brand">
    <Link to="/">
      <img
        src="images/newLogoSideWays.png"
        width="142"
        height="38"
        alt="RankCasts Logo" />
    </Link>

    <span
      role="button"
      class="navbar-burger burger"
      aria-label="menu"
      aria-expanded="false"
      data-target="navbarBasicExample">
      <span></span>
      <span></span>
      <span></span>
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
          <Link>Categories &dtrif;</Link>
          <div class="navbar-dropdown">
            <Link to="#">
              <span class="d-link">General</span>
            </Link>
            <Link to="/politics">
              <span class="d-link">Political</span>
            </Link>
            <Link to="/comedy">
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
          <button id="sign-up-button" class="button is-project-primary">
            <strong>Sign up</strong>
          </button>
          <button id="login-button" class="button is-outlined">Log in</button>
        </div>
      </div>
    </div>
  </div>
</nav>
