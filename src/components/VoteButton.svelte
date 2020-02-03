<script>
  export let count = 0;

  function handleVote() {
    count += 1;
  }
</script>

<style>
  .ranking-p {
    text-align: center;
    color: #3a3a3a;
  }
</style>

<button on:click={handleVote} class="button is-dark">&#x25B2;</button>
<p class="ranking-p">Votes: {count}</p>
