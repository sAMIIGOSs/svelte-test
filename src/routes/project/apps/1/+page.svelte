
<script>

import {Icon} from '../../../../components/Icon.svelte';


let newItem ="";
let todoList = [];

function add() {
    if(newItem !== "") {
        todoList = [
            ...todoList,
            {
                task: newItem,
                completed: false,
            },
        ];
        newItem = "";
    }
}

function remove(index) {
        todoList.splice(index, 1);
        todoList = [...todoList]; 
    }

    function complete(index) {
        todoList[index].completed = !todoList[index].completed;
        todoList = [...todoList]; 
    }


</script>

<main>
    <h1>My to-do list</h1>
    <form on:submit|preventDefault={add}>
        <input bind:value={newItem} placeholder="Enter to-do" />
        <button class="add-todo" on:click={add}><span>+</span></button>
    </form>
    <div class="todos">
        {#each todoList as item, index}
        <div class="todo" class:completed={item.completed}>
            <span class="todo__text">{item.task}</span>
            <div class="todo__buttons">
                <button class="complete" on:click={()=> complete(index)}>
                    <Icon name="check-mark" />
                </button>
                    <button class="delete" on:click={() => remove(index)}>
                    <Icon name="delete" />
                    </button>
            </div>
        </div>
        {/each}
    </div>
</main>

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
        width: 0;
        border: none;
        border-bottom: 1px solid black;
        background: transparent;
        box-shadow: none;
        font-size: 1.2rem;
        margin: 0;
        outline: none;
    }
</style>