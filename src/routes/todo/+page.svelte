<script lang="ts">
    let todos:string[] = [];
    let newTodo = '';

    const addTodo = () => {
        if (newTodo.trim() !== '') {
            todos = [...todos, newTodo];
            newTodo = '';
        }
    }

    const removeTodo = (index:number) => {
        todos = todos.filter((_, i) => i !== index);
    }
</script>

<main>
    <h1>Todo List</h1>

    <input type="text" bind:value={newTodo} placeholder="Add a new todo" />
    <button on:click={addTodo}>Add</button>

    <ul>
        {#each todos as todo, index}
            <li>
                {todo}
                <button on:click={() => removeTodo(index)}>Remove</button>
            </li>
        {/each}
    </ul>
</main>

<style>
    /* Add your custom styles here */
</style>