<script>
  export let addTodo;
  
  let inputEmpty = true;
  let newTodo = '';

  function formSubmited(e){
    addTodo(newTodo)
    newTodo = '';
  }
</script>

<form on:submit|preventDefault={formSubmited}>
  <label>
    New Todo
    <input bind:value={newTodo} type="text" placeholder="Enter a todo...">
  </label>
  <button disabled={newTodo === '' ? true : false}>Add Todo</button>
</form>

<style>
  button {
    background-color: rgb(83, 113, 232);
  }
</style>