<script>
  import { onMount } from 'svelte'
  import '../node_modules/bulma/css/bulma.min.css'
  import Sidebar from './components/Sidebar.svelte'
  import Nav from './components/Nav.svelte'
  import Footer from './components/Footer.svelte'
  import { Router, Route } from 'svelte-routing'
  import Home from './pages/Home.svelte'
  import About from './pages/About.svelte'
  import Comedy from './pages/Comedy.svelte'
  import Politics from './pages/Politics.svelte'

  let showNavbar = false

  onMount(() => {
    const mediaListener = window.matchMedia('(max-width: 767px)')
    mediaListener.addEventListener('change', e => {
      showNavbar = e.matches
    })
  })

  export let url = ''
</script>

<style>

</style>

<div class="columns">
  <Router {url}>
    {#if showNavbar != false}
      <Nav />
    {:else}
      <Sidebar />
    {/if}
    <div class="container">
      <Route path="/" component={Home} />
      <Route path="/about" component={About} />
      <Route path="/comedy" component={Comedy} />
      <Route path="/politics" component={Politics} />
    </div>
  </Router>
  <slot />

</div>

<Footer />
