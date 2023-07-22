<script>
    import CircleButton from "./CircleButton.svelte";
    let newTodo = "";
    let todos = [];

    function addTodo() {
      if (newTodo.trim() !== "") {
        todos = [...todos, newTodo.trim()];
        newTodo = "";
      }
    }

    function removeTodo(index) {
      todos = todos.filter((_, i) => i !== index);
    }
</script>

<style>
    .todo-list {
      list-style: none;
    }
    .todo-list li {
      display: flex;
      align-items: center;
    }
    .todo-list li .remove-button {
      margin-right: 10px;
    }
</style>

<div>
    <input type="text" bind:value={newTodo} on:keydown={(e) => e.key === 'Enter' && addTodo()} placeholder="New todo" />
    <button on:click={addTodo}>Add</button>
</div>
<ul class="todo-list">
    {#each todos as todo, index (index)}
        <li>
            <CircleButton onClick={() => removeTodo(index)} />
            <p>{todo}</p>
        </li>
    {/each}
</ul>
