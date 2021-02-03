<script>
	import Navbar from './Navbar.svelte';

	let todo = '';
	let todos = [];

	const submitTodo = () => {
		todos = [...todos, todo];
		todo = '';
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
		{#each todos as todo}
			<p>{todo}</p>
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