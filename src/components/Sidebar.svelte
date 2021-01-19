<script>
  import { Link } from 'svelte-routing'
</script>

<style>
  .sidebar {
    margin-top: 25px;
    margin-right: 5px;
  }
  .menu-label {
    margin-left: 45px;
    font-weight: 600;
    color: #ccb20c;
  }

  .menu-list {
    margin-left: 45px;
  }

  img {
    margin-left: 5px;
  }

  .menu-list :global(a) {
    text-decoration: none;
    display: block;
    color: #9624c4;
  }

  .menu-list :global(a:hover) {
    text-decoration: none;
    color: #ccb20c;
    background-color: #ffffff;
  }

  .menu-list :global(a:active) {
    color: #3f3f3f;
    text-shadow: 2px 2px 8px rgba(195, 0, 255, 0.65);
  }

  /*
  TODO:
  This is causing a purple line accross the middle of the screen.
    .menu-list :global(a::after) {
    position: absolute;
    content: '';
    width: calc(100% - 1em);
    height: 2px;
    background-color: rgb(195, 0, 255);
    display: block;
    bottom: -1px;
  } */
</style>

<div class="column sidebar is-1">
  <aside class="menu">
    <Link to="/">
      <img
        src="images/newLogoSideWays.png"
        width="142"
        height="38"
        alt="RankCasts Logo"
      />
    </Link>
    <p class="menu-label">General</p>
    <ul class="menu-list">
      <li>
        <Link to="/">Home</Link>
      </li>
      <li>
        <Link to="/about">About</Link>
      </li>
      <li>
        <Link to="/contact">Contact</Link>
      </li>
    </ul>
    <p class="menu-label">Categories</p>
    <ul class="menu-list">
      <li>
        <Link to="/">General</Link>
      </li>
      <li>
        <Link to="/comedy">Comedy</Link>
      </li>
      <li>
        <Link to="/politics">Politics</Link>
      </li>
      <li>
        <Link to="/">Developer</Link>
      </li>
    </ul>
    <p class="menu-label">Transactions</p>
    <ul class="menu-list">
      <li>
        <Link to="/">Payments</Link>
      </li>
      <li>
        <Link to="/">Transfers</Link>
      </li>
      <li>
        <Link to="/">Balance</Link>
      </li>
    </ul>
  </aside>
</div>
