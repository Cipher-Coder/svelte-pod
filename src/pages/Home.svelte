<script>
  import VoteButton from '../components/VoteButton.svelte'
  import SubmitForm from '../components/SubmitForm.svelte'

  let posts = []
  ;(async () => {
    const res = await fetch(
      'https://v2-api.sheety.co/0b5f365fe37e4932db5dabe9775b63d0/podcastList/podcasts',
    )
    posts = (await res.json()).podcasts
  })()
</script>

<style>
  h1 {
    font-size: 2rem;
    font-weight: bold;
    margin: 25px 20px;
  }

  h3 {
    font-size: 1.25rem;
    margin: 20px 10px;
  }

  .focus-in-expand {
    animation: focus-in-expand 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94) both;
    -webkit-animation: focus-in-expand 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94)
      both;
  }

  @-webkit-keyframes focus-in-expand {
    0% {
      letter-spacing: -0.5em;
      -webkit-filter: blur(12px);
      filter: blur(12px);
      opacity: 0;
    }
    100% {
      -webkit-filter: blur(0px);
      filter: blur(0px);
      opacity: 1;
    }
  }
  @keyframes focus-in-expand {
    0% {
      letter-spacing: -0.5em;
      -webkit-filter: blur(12px);
      filter: blur(12px);
      opacity: 0;
    }
    100% {
      -webkit-filter: blur(0px);
      filter: blur(0px);
      opacity: 1;
    }
  }

  .media-right {
    float: right;
    margin-top: -70px;
    margin-right: 45px;
  }

  .is-right {
    float: right;
    padding-left: 75px;
  }

  .submit-title {
    font-size: 1.5rem;
    margin-bottom: 15px;
  }
</style>

<svelte:head>
  <title>Home | Rank Pods</title>
</svelte:head>
<div class="container">

  <h1 class="focus-in-expand">Rank The Best Podcasts:</h1>
  <div class="container">
    <div class="column is-one-third is-right">
      <div class="row">
        <h2 class="submit-title">Submit An Awesome Podcast!</h2>
        <SubmitForm />
      </div>
    </div>
    {#each posts as post}
      <div class="column is-two-thirds s6">
        <div class="card">
          <div class="card-content">
            <div class="media">
              <div class="media-left">
                <figure class="image is48x48">
                  <img src={post.image} alt="Album Cover" />
                </figure>
              </div>
            </div>
            <div class="media-content">
              <p class="title is-5">{post.name}</p>
            </div>
            <div class="media-right">
              <VoteButton />
            </div>
          </div>
        </div>
      </div>
    {:else}
      <p>No posts</p>
    {/each}

  </div>

  <h3>More to Come!!!</h3>

</div>
