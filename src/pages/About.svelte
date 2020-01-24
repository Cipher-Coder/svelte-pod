<script>

</script>

<style>
  .intro {
    margin: 45px 0;
  }

  .microphone {
    border-radius: 6px;
  }

  h1 {
    font-size: 2rem;
    font-weight: bold;
  }

  h2 {
    font-size: 1.75rem;
    font-weight: bold;
    margin: 15px 0;
  }

  .writing {
    font-size: 1rem;
    line-height: 1.2rem;
  }

  .is-centered {
    text-align: center;
  }

  .projects {
    margin: 45px 0;
  }

  .devtabs {
    margin: auto;
    justify-content: center;
  }

  .devtabs-img {
    max-width: 800px;
    margin: auto;
  }

  .caption {
    margin-left: 15px;
    font-size: 1.2rem;
  }
</style>

<svelte:head>
  <title>About | Top Podcasts</title>
</svelte:head>

<div class="container intro">
  <div class="columns">
    <div class="column">
      <img
        class="microphone"
        src="images/microphone1.jpg"
        alt="Professional microphone" />
    </div>
    <div class="column">
      <h1 class="is-centered">About Developer Podcasts</h1>
      <p class="writing">
        Podcasts have become a cultural phenomenon! They can inform, teach,
        entertain, and much much more!
      </p>
    </div>
  </div>
  <div class="container projects is-centered">
    <h2>Check out some of my other projects:</h2>
  </div>
  <div class="devtabs columns">
    <figure>
      <img
        class="devtabs-img column"
        src="images/devtabs.png"
        alt="Screenshot of Dev Tabs" />
      <figcaption class="caption">Dev Tabs Browser Extension</figcaption>
    </figure>

  </div>

</div>
