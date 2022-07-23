<script>
  import PlayerCounter from './lib/PlayerCounter.svelte'
  const pageTitle = 'Svelte Player Counter'
</script>
<section>
  <h1>{pageTitle}</h1>
  <div class="wrapper">
    <PlayerCounter playerName="Lennon"></PlayerCounter>
    <PlayerCounter playerName="McCartney"></PlayerCounter>
  </div>
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
</style>
