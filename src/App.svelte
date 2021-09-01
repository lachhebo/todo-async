<script>
	$:tasks = [];
	let addtask = '';

	function addTask(){
		let newtask = {
			//'id': tasks.length +1,
			'status': 'Unstarted',
			'value': addtask
		}
		tasks = [...tasks, newtask]
		console.log(tasks);
	}


</script>

<main>
	<h1>Best TODO APP for Skooleurs ! </h1>

	<div>
		<input bind:value={addtask} type="text" id="addtask">
		<button on:click={addTask}>add a task</button>
	</div>

	<div>
		{#each tasks as task, i}
			<li>
				{task.value}
			</li>
		{/each}
	</div>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>