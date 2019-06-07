<script>
  import { createEventDispatcher } from "svelte";
  const displatch = createEventDispatcher();

  let newMemeber = {
    name: "",
    imageSrc: "",
    score: 0
  };

  const onSubmit = e => {
    e.preventDefault();

    displatch("addmember", newMemeber);

    newMemeber = {
      name: "",
      imageSrc: "",
      score: 0
    };
  };
</script>

<style>
  .form {
    margin-top: 1rem;
    display: flex;
    flex-direction: column;
    max-width: 400px;
    margin: 1rem auto 0;
  }
  .form input {
    border-radius: 5px;
    background: transparent;
    color: var(--secondary-color);
  }
</style>

<form class="form" on:submit={onSubmit}>
  <label>
    <strong>Enter Image Path</strong>
    <input type="text" bind:value={newMemeber.imageSrc} />
  </label>
  <input type="text" placeholder="Enter a name" bind:value={newMemeber.name} />
  <input type="number" bind:value={newMemeber.score} />
  <button class="btn">ADD</button>
</form>
