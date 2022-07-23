<script>
  
  export let playerName;
  
  export let playerScore = 0;
  
  function addPoint(){
    return playerScore += 1;
  }
  
  function decreasePoint(){
    if (playerScore > 0) {
      return playerScore -= 1;
    }
  }

  export function reset(){
    playerScore = 0;
  }
</script>

<div class="player-counter">
  <h2>{playerName}</h2>
  <h3>Player Score: {playerScore}</h3>
  <button on:click={addPoint}>+</button>
  <button on:click={decreasePoint}>-</button>
</div>

<style>
  .player-counter {
    padding: 25px;
  }
  .player-counter button:nth-of-type(1) {
    background-color: rgb(80, 80, 226);
  }
  .player-counter button:nth-of-type(2) {
    background-color: rgb(240, 93, 93);
  }
</style>