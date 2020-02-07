<script>
  let searchParam = ''
  let baseurl = `https://itunes.apple.com`
  let url
  let result
  let searchResult = []

  async function searchForPodcast() {
    let searchTerm = searchParam
    let query = `/search?term=${searchTerm}&entity=podcast`
    url = encodeURI(baseurl + query)

    try {
      let response = await fetch(url)
      let data = await response.json()
      searchResult = data['results']
      console.log('Success: ', data)
    } catch (err) {
      console.log('Error: ', err)
    }
  }

  function submissionHandler(e) {
    result = searchForPodcast()
    searchParam = ''
  }
</script>

<style>
  .submit-title {
    font-size: 1.5rem;
    margin-bottom: 15px;
  }

  h4 {
    font-size: 1.1rem;
    font-weight: bold;
  }
</style>

<article>
  <h2 class="submit-title">Search for Podcast</h2>
  <form on:submit|preventDefault={submissionHandler}>
    <label for="name">Search:</label>
    <input bind:value={searchParam} id="search" type="text" />

    <button type="submit" id="searchbutton">Submit</button>
  </form>
  <div>
    {#if result === undefined}
      <p>Search for: {searchParam}</p>
    {:else}
      {#await result}
        <p>Loading...</p>

      {:then results}
        <h4>Results:</h4>
        <ul>
          {#each searchResult as searchResults}
            <li>{searchResults.artistName}</li>
          {/each}
        </ul>
      {:catch error}
        <p>{error.message}</p>

      {/await}
    {/if}

  </div>

</article>
