<script>
    import { todoList } from "../util/AppStore";
    export let todoContent;
    let completed = false;

    const complete = () => {
        completed = !completed;
    }

    const remove = () => {
        todoList.update(list => list.splice(list.indexOf(todoContent), 1));
    }
</script>

<div class="wrapper">
    <p class:completed>{todoContent}</p>
    <button on:click={complete}>Done</button>
    <button class="delete" on:click={remove}>Remove</button>
</div>

<style>
    .wrapper {
        width: 100%;
        display: flex;
        justify-content: space-between;
    }

    .completed {
        text-decoration: line-through;
        color: #333;
    }

    button {
        margin: .5rem 1rem;
        font-size: 12pt;
        font-weight: lighter;
        text-transform: uppercase;
        padding: .5rem 2rem;
        background: none;
        border: solid 2px rgba(37, 145, 251, 0.98);
    }

</style>