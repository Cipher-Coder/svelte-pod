<script>
  import "../node_modules/bulma/css/bulma.min.css";
  import Nav from "./components/Nav.svelte";
  import { Router, Route } from "svelte-routing";
  import Home from "./pages/Home.svelte";
  import About from "./pages/About.svelte";
</script>

<style>

</style>

<Router>
  <Nav />
  <div class="container">
    <Route path="/" component={Home} />
    <Route path="/about" component={About} />
  </div>

</Router>
