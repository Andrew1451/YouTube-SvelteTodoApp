<script>
	import Navbar from './Navbar.svelte';
	import Todo from './Todo.svelte';

	let todo = '';
	let todos = [];

	const submitTodo = () => {
		todos = [...todos, todo];
		todo = '';
	}
	const deleteTodo = event => {
		todos = todos.filter((todo, i) => i !== event.detail);
	}

</script>

<Navbar />
<main>
	<form>
		<input type='text' required bind:value={todo} />
		<button type='submit' on:click|preventDefault={submitTodo}>Submit</button>
	</form>
	{#if todos.length === 0}
		<p>Add todos!</p>
	{:else}
		{#each todos as todo, index}
			<Todo todo={todo} index={index} on:delete={deleteTodo} />
		{/each}
	{/if}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	input:focus {
		outline: none;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>