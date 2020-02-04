<script>
  export let className = ''
  export let src = ''
  export let alt = ''
</script>

<style>
  img {
    border-radius: 6px;
    -webkit-box-shadow: rgba(26, 26, 67, 0.05) 1px 1px 5px 0px,
      rgba(50, 50, 93, 0.5) -39px 62.5px 125px -25px,
      rgba(0, 0, 0, 0.3) 23.4px 37.5px 75px -37.5px;
    box-shadow: rgba(26, 26, 67, 0.05) 1px 1px 5px 0px,
      rgba(50, 50, 93, 0.5) -39px 62.5px 125px -25px,
      rgba(0, 0, 0, 0.3) 23.4px 37.5px 75px -37.5px;
  }
</style>

<img {src} {alt} class={className} />
