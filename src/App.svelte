<script>
  import TodoForm from "./lib/TodoForm.svelte";
  import TodoItems from "./lib/TodoItems.svelte";
  const pageTitle = 'Todo App'
  let todosArr = localStorage.getItem('todos') ? JSON.parse(localStorage.getItem('todos')) : [];

  function addTodo(todoInput){
    todosArr.push({
      title: todoInput,
      done: false,
    })
    todosArr = todosArr;
  }

  function deleteTodo(removeItemIndex){
    todosArr.splice(removeItemIndex, 1);
    todosArr = todosArr;
  }

  function changeDone(updateItemIndex){
    let initialStatus = todosArr[updateItemIndex].done;
    todosArr[updateItemIndex].done = !initialStatus;
  }

  $: localStorage.setItem('todos', JSON.stringify(todosArr));

</script>

<main>
  <h1>{pageTitle}</h1>
  <TodoForm addTodo={addTodo} />
  <TodoItems todoItemsArr={todosArr} deleteItem={deleteTodo} updateStatus={changeDone}/>
</main>

<style>

</style>
