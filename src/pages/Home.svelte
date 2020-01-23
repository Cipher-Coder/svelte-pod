<script>
  let posts = [];

  (async () => {
    const res = await fetch(
      "https://v2-api.sheety.co/0b5f365fe37e4932db5dabe9775b63d0/podcastList/podcasts"
    );
    posts = (await res.json()).podcasts;
  })();
</script>

<style>
  h3 {
    font-size: 22px;
    margin: 5px 25px;
  }
</style>

<div class="row">

  <h3>Best Developer Podcasts:</h3>

  {#each posts as post}
    <div class="col s6">
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

        </div>
      </div>
    </div>
  {:else}
    <p>No posts</p>
  {/each}

  <h3>More Coming!!!</h3>

</div>
