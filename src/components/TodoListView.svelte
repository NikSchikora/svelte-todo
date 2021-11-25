<script>
    import { todoList } from "../util/AppStore";
    import TodoItem from "./TodoItem.svelte";
</script>

{#each $todoList as item}
    <TodoItem todoContent={item} />
{/each}