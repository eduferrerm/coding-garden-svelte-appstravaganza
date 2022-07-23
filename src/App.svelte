<script>
  import PlayerCounter from './lib/PlayerCounter.svelte'
  const pageTitle = 'Svelte Player Counter'
  let player1Score = 0;
  let player2Score = 0;

  function resetScores(){
    player1Score = 0;
    player2Score = 0;
  }

</script>

<section>
  <h1>{pageTitle}</h1>
  <div class="wrapper">
    <PlayerCounter 
      bind:playerScore={player1Score}
      playerName="Lennon"
    ></PlayerCounter>
    <PlayerCounter 
      bind:playerScore={player2Score}
      playerName="McCartney"
    ></PlayerCounter>
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
