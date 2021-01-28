<script lang="ts">
	import Navbar from './Navbar.svelte';
	import Todo from './Todo.svelte';
	import AddTask from './AddTask.svelte'

	let a = [
	]

	const handleDelete = (id) => {
		const arr = a.filter(curr => curr.id !== id);
		console.log(id)
		a = arr;
	}

	const addTask = (task, resetForm) => {
		let nextId = a.length === 0 
			?
			0
			:
			a[a.length - 1].id + 1

		let arr = [{
			listItem: task.title,
			description: task.desc,
			id: nextId
		}, ...a]
		a = arr
		resetForm();
	}
</script>

<Navbar />
<main>
	<h1>TO-DO</h1>
	<AddTask addTask={addTask}/>
	{#each a as b}
		<Todo listItem={b.listItem} description={b.description} handleDelete={handleDelete} id={b.id}/>
	{/each}
</main>

<style>
	main {
		padding: 0;
		margin: 0;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	
	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
		margin: 0;
		margin-bottom: 1.05rem;
		padding: 0;
	}
</style>