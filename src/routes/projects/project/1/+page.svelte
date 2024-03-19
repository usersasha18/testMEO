<svelte:head>
    <title>Список портфолио</title>
</svelte:head>

<main>
    <form on:submit={add}>
        <input bind:value={newItem} placeholder="Enter todo...">
        <button class="add-todo" on:click={add}><span>+</span></button>
    </form>
    <div class="todos">
        {#each todoList as todo, index}
            <span class="todo-index">{todo.task}</span>
            <div class="todo-button">
                <button class="complete" on:click={() => complete(index)}>
                    <Icon name="check-mark"/>
                </button>
                <button class="delete" on:click={() => remove(index)}>
                    <Icon name="delete"/>
                </button>
            </div>
        {/each}
    </div>
</main> 

<script>

    import Icon from "../../../../components/Icon.svelte";

    let newItem=""
    let todoList = []

    function add(){
        if(newItem !== '') {
            todoList = [
                ...todoList,
                {
                    task: newItem,
                    isCompleted: false
                }
            ];
            newItem = "";
        }
    }

    function remove(index) {
        todoList.slice(index, 1)
        todoList = todoList
    }
    function complete(index) {
        todoList[index].isCompleted = !todoList[index].isCompleted
    }
</script>

<style>

    main {
        display: flex;
        flex-direction: column;
        align-items: center;
        min-height: 100%;
        padding: 5vmin;
        box-sizing: border-box;
        background: antiquewhite;
    }

    form {
        width: 100%;
        max-width: 500px;
        display: flex;
        align-items: center;
        margin-bottom: 1rem;
    }

    input {
        flex-grow: 1;
        border: none;
        border-bottom: 1px solid black;
        background: transparent;
        font-size: 1.2rem;
        outline: none;
    }

    .todo {
        display: flex;
        padding: 20px;
        border-radius: 20px;
        box-shadow: 0 0 15px rgb(0,0,0 / 20%);
        background-color: hsl(0, 0%, 100%, 0.2);
        margin-top: 1rem;
        font-size: 1.2rem;
        justify-content: space-between;
        align-items: center;
    }
    .todo-button {
        display: flex;
        align-items: center;
        margin-left: 1rem;
    }
    .todo button {
        width: 32px;
        height: 32px;
        padding: 4px;
        margin: 0;
        flex-shrink: 0;
    }

    h1 {
        text-align: center;
        font-size: 1.5rem;
        margin: 2rem 0;
    }
</style>