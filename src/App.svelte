<script>
import TodoListView from "./components/TodoListView.svelte";

	let todo = "";
	import { todoList } from "./util/AppStore";
	const addNewToDo = () => {
		if(todo.length == 0) return;
		todoList.update((todos) => [todo, ...todos]);
		console.log("Added new Todo: " + todo);
		todo = "";
	}
</script>

<div class="wrapper">
	<main class="card">
		<h1>ToDo-Liste</h1>
		<div class="todoControls">
			<input type="text" name="todo" placeholder="New ToDo-Item" bind:value={todo}>
			<button on:click={addNewToDo} >Add</button>
		</div>
		<div class="todoItems">
			<TodoListView />
		</div>
	</main>
	
</div>

<style>

	button {
		margin: .5rem 1rem;
		font-size: 12pt;
		font-weight: lighter;
		text-transform: uppercase;
		padding: .5rem 2rem;
		background: none;
		border: solid 2px rgba(37, 145, 251, 0.98);
	}

	.wrapper {
		width: 100%;
		height: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		background-image: radial-gradient( circle farthest-corner at 10% 20%,  rgba(37,145,251,0.98) 0.1%, rgba(0,7,128,1) 99.8% );	}

	.card {
		text-align: center;
		max-width: 25rem;
		background-color: #fff;
		box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
		padding: 2rem 4rem;
		border-radius: 20px;
		margin-bottom: 10rem;
	}

	h1 {
		color: #262626;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: normal;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}

</style>