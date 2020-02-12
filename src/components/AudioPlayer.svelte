<script context="module">
  let current
</script>

<script>
  export let audioSrc
  let audio
  let paused = true

  function stopOthers() {
    if (current && current !== audio) current.pause()
    current = audio
  }
</script>

<style>
  audio {
    width: 100%;
    margin: 0.5em 0 1em 0;
  }
  .playing {
    color: red;
  }
</style>

<article class:playing={!paused}>
  <audio
    bind:this={audio}
    bind:paused
    on:play={stopOthers}
    src={audioSrc}
    controls />

</article>
