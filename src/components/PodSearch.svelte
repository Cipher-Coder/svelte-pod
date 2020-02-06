<script>
  let searchParam = ''
  let baseurl = `https://itunes.apple.com`

  let url

  let searchForPodcast = () => {
    let searchTerm = searchParam
    let query = `/search?term=${searchTerm}&entity=podcast`
    url = encodeURI(baseurl + query)
    console.log(url)
    fetch(url)
      .then(response => response.json())
      .then(data => {
        console.log('success: ', data)
      })
      .catch(error => {
        console.error('Error:', error)
      })
  }
</script>

<style>
  .submit-title {
    font-size: 1.5rem;
    margin-bottom: 15px;
  }
</style>

<article>
  <h2 class="submit-title">Search for Podcast</h2>
  <form on:submit|preventDefault={searchForPodcast}>
    <label for="name">Search:</label>
    <input bind:value={searchParam} id="search" type="text" />

    <button type="submit" id="searchbutton">Submit</button>
  </form>
  <div id="search-results">

    <p>{searchParam}</p>

  </div>

</article>
