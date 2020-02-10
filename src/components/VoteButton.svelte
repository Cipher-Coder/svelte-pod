<script>
  export let count = 0
  let url = ''

  postRequest(
    'https://v2-api.sheety.co/0b5f365fe37e4932db5dabe9775b63d0/podcastList/podcasts',
    { likes: count },
  )
    .then(data => console.log(data))
    .catch(error => console.error(error))

  function postRequest(url, data) {
    return fetch(url, {
      credentials: 'same-origin',
      method: 'PUT',
      body: JSON.stringify(data),
      headers: new Headers({
        'Content-Type': 'application/json',
      }),
    }).then(response => response.json())
  }

  function handleVote() {
    count += 1
  }
</script>

<style>
  .ranking-p {
    text-align: center;
    color: #3a3a3a;
  }
</style>

<button on:click={handleVote} class="button is-white">&#128077;</button>
<p class="ranking-p">Votes: {count}</p>
