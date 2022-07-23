<script>
  import PlayerCounter from './lib/PlayerCounter.svelte'
  const pageTitle = 'Svelte Player Counter'
  let player1Component;
  let player2Component;

  function resetScores(){
    player1Component.reset();
    player2Component.reset();
  }
</script>

<section>
  <h1>{pageTitle}</h1>
  <div class="wrapper">
    <PlayerCounter bind:this={player1Component} playerName="Lennon"></PlayerCounter>
    <PlayerCounter bind:this={player2Component} playerName="McCartney"></PlayerCounter>
  </div>
  <button class="secondary" on:click={resetScores}>Reset</button>
</section>

<style>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .wrapper {
    display: flex;
  }
  button {
    border: 1px solid #efefef;
  }
</style>
