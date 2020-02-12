<script>
  import '../node_modules/bulma/css/bulma.min.css'
  import Nav from './components/Nav.svelte'
  import Footer from './components/Footer.svelte'
  import { Router, Route } from 'svelte-routing'
  import Home from './pages/Home.svelte'
  import About from './pages/About.svelte'
  import Comedy from './pages/Comedy.svelte'
  import Politics from './pages/Politics.svelte'

  export let url = ''
</script>

<style>

</style>

<Router {url}>
  <Nav />
  <div class="container">
    <Route path="/" component={Home} />
    <Route path="/about" component={About} />
    <Route path="/comedy" component={Comedy} />
    <Route path="/politics" component={Politics} />
  </div>

</Router>
<slot />
<Footer />
