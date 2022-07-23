<script>
  
  export let playerName;
  
  export let playerPoint = 0;
  
  function addPoint(){
    return playerPoint += 1;
  }
  
  function decreasePoint(){
    if (playerPoint > 0) {
      return playerPoint -= 1;
    }
  }

  export function reset(){
    playerPoint = 0;
  }
</script>

<div class="player-counter">
  <h2>{playerName}</h2>
  <h3>Player Score: {playerPoint}</h3>
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