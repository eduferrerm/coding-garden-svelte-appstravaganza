<script>
  export let todoItemsArr;
  export let updateStatus;
  export let deleteItem;
</script>

<section class="todo-container">
  <ul class="items-list">
    {#each todoItemsArr as {title, done}, i }
      <li>        
        <p>
          {#if done}✅{/if}
          <span class:item-done={done}>{title}</span>
        </p>
        <div class="item-options">
          <input bind:checked={done} type="checkbox" on:click={updateStatus(i)}>
          <button class="item-delete" on:click={deleteItem(i)}>🗑️</button>
        </div>
      </li>
    {/each}
  </ul>
</section>

<style>
  .items-list {
    text-align: left;
    margin: 0;
    padding: 0;
  } 
  .items-list li {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border: 1px solid #efefef;
    padding: 16px;
    margin: 0 0 8px 0;
    border-radius: 5px;
  }
  .items-list p {
    margin: 0 16px 0 0;
  }
  .item-options {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .item-done {
    text-decoration: line-through;
  }
  .item-delete {
    background-color: transparent;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 40px;
    height: 40px;
    margin-bottom: 0;
  }
</style>  