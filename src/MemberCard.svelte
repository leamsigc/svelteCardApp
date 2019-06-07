<script>
  export let name;
  export let score;
  export let imageSrc;
  const addPoints = () => (score = score + 1);
  const minusOneScore = () => (score = score - 1);
</script>

<style>
  .card {
    max-width: 300px;
    border: 1px solid #414141;
    box-shadow: 0 19px 38px rgba(0, 0, 0, 0.3), 0 15px 12px rgba(0, 0, 0, 0.22);
    border-radius: 5px;

    padding: 0.2rem;
    background: #333333;
    text-align: left;
    flex: 1 1 300px;
    margin: 5px 0 5px 5px;
    color: var(--white-color);
  }
  .card__title {
    font-size: 1.5rem;
    line-height: 1.6;
    /* margin-bottom: 1rem; */
    color: var(--white-color);

    font-weight: 500;
    text-align: center;
    padding: 0.5rem 2rem;
  }
  .card__score {
    padding: 1rem 2rem;
    color: #919191;
  }
  .card__score span {
    font-weight: 900;
    color: var(--yellow-color);
    background: var(--main-color);
  }
  .card__controllers {
    padding: 0.5rem 2rem;
    margin-bottom: 0.5rem;
    display: flex;
  }
  .card__controllers button {
    margin-left: 1rem;
    color: var(--white-color);
  }
  .card__img {
    padding: 0.3rem 0.1rem 1rem;
    width: 100%;
    /* background: var(--white-color); */
  }
  .card__img img {
    display: block;
    height: 200px;
    width: 100%;
    border-radius: 5px;
  }
</style>

<div class="card">
  <div class="card__img">
    <img
      src={imageSrc}
      alt="Daytona Dev Solutions Svelte app Development Daytona Beach" />
  </div>
  <div class="card__title "> {name} </div>
  <div class="card__score">
    Score:
    <span class="yellow"> {score}</span>
  </div>
  <div class="card__controllers">
    <buttton class="btn btn-small" on:click={addPoints}>+</buttton>
    <button class="btn btn-main btn-small" on:click={minusOneScore}>-</button>
  </div>
</div>
