<script>
  export let count = 0

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
