<script>
  export let count = 0
  let url = ''

  function handleVote() {
    count += 1
  }
</script>

<style>
  button {
    background-color: #ffffff00;
  }
  .ranking-p {
    text-align: center;
    color: #3a3a3a;
  }
</style>

<button on:click={handleVote} class="button">&#128077;</button>
<p class="ranking-p">Upvotes: {count}</p>
