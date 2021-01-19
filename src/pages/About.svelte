<script>
  import Image from '../components/Image.svelte'
  let myImage = {
    src: 'images/audioBoard.jpg',
    alt: 'Audio Board',
    className: 'pic',
  }

  let microphone = {
    src: 'images/microphone1.jpg',
    alt: 'Professional Microphone',
    className: 'microphone',
  }
</script>

<style>
  .intro {
    margin: 45px 0;
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
    font-size: 1.1rem;
    line-height: 1.2rem;
  }

  .projects {
    margin: 45px 0;
  }

  .devtabs {
    margin: auto;
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    justify-content: center;
  }

  .devtabs-img {
    max-width: 800px;
    margin: auto;
    border-radius: 16px;
  }

  .caption {
    margin-left: 15px;
    font-size: 1.2rem;
  }

  .addedPic {
    max-width: 600px;
    text-align: center;
    margin: 40px auto 60px;
  }
</style>

<svelte:head>
  <title>About | RankCasts</title>
</svelte:head>
<div class="container">
  <div class="container intro">
    <div class="columns is-vcentered">
      <div class="column">
        <Image {...microphone} />
      </div>
      <div class="column">
        <h1 class="has-text-centered">About Dev Pods</h1>
        <p class="writing">
          Podcasts have become a cultural phenomenon! They can inform, teach,
          entertain, and much much more! Everyone loves them, including me!
        </p>
        <p class="writing">
          The problem I encountered was there was no where I could go and just
          type in "Developer Podcasts" and find them. Not just find them, but
          find the good ones. I searched and searched. Made my own list... but
          then I had to spend the time listeneing to every single one, just to
          find out which one was good. This has taken hours and I am still
          finding more and more that I want to try out.
        </p>
        <p class="writing">
          The solution... Dev Pods. Here you can submit podcasts that you like,
          have listened to, and want to recommend. The community can rank them
          so when anyone looks at the page they know immediately which podcasts
          are great.
        </p>
      </div>
    </div>
    <div class="container projects">
      <h2 class="has-text-centered">Check out some of my other projects:</h2>
    </div>
    <div class="devtabs columns">
      <figure class="figure-container">
        <img
          class="devtabs-img column"
          src="images/devtabs.png"
          alt="Screenshot of Dev Tabs"
        />
        <figcaption class="caption">
          <a
            href="https://mattaz.com/devtabs"
            target="_blank"
            rel="noopener noreferrer"> Dev Tabs Browser Extension </a>
        </figcaption>
      </figure>
    </div>
  </div>
  <div class="addedPic">
    <Image {...myImage} />
  </div>
</div>
