<script>
  export let error_boolean = false

  async function handleSubmit(event) {
    console.log(event)
    console.log(event.target)
    console.log(event.target.podcastName.value)
    console.log(event.target.podcastUrl.value)
  }

  function validateForm(e) {
    let textbox = event.target
    error_boolean = false
    if (textbox.value === '') {
      textbox.setCustomValidity('Podcast URL Required!!')
    } else if (textbox.validity.typeMismatch) {
      error_boolean = true
      textbox.setCustomValidity('Please enter a valid URL')
    } else {
      textbox.setCustomValidity('')
    }
    return true
  }
</script>

<style>
  article {
    margin-bottom: 35px;
  }
  .form-error {
    font-size: 1.1rem;
    color: red;
  }

  .submit-title {
    font-size: 1.5rem;
    margin-bottom: 15px;
  }

  button {
    background-color: #9624c4;
    border: 1px solid transparent;
    color: #fff;
    font-size: 1rem;
    font-weight: normal;
  }

  button:hover {
    background-color: #712391e1;
    border: 1px solid transparent;
    color: #fff;
    font-size: 1rem;
  }

  input:focus {
    outline: 1px solid rgb(167, 167, 167);
  }
</style>

<article class="container">
  <h2 class="submit-title">Submit An Awesome Podcast!</h2>
  <form
    id="podcast-submission"
    class="submit-podcast"
    on:submit|preventDefault={handleSubmit}
    on:invalid={validateForm}
    on:changed={validateForm}
    on:input={validateForm}>
    <label for="podcastName">Podcast Name:</label>
    <input required type="text" id="podcastName" />
    <label for="podcastUrl">Podcast Feed URL</label>
    <input required type="url" id="podcastUrl" />
    <br />
    {#if error_boolean}
      <h2 class="form-error">Error!! Check your submission!</h2>
    {/if}

    <button class="button" type="submit">Submit</button>

  </form>

</article>
