<template>
	<div id="app">
		<div class="todoapp">
			<app-header
				@addTodo="addTodo"
			/>
			<todo-list
				:viewTodos="viewTodos"
				@editTodo= "editTodo"
				@deleteTodo="deleteTodo"
				@completedTodo="completedTodo"
				@toggleAllTodo="toggleAllTodo"
			></todo-list>
			<app-footer
				:todoFilters="todoFilters"
				:currentLocation="currentLocation"
				@changeLocation="changeLocation"
				:leftItems="this.$store.state.todos.filter( v => v.isDone === true).length"
			></app-footer>
		</div>
	</div>
</template>

<script lang="ts">
	import App from './App.ts'

	export default App
</script>

<style lang="scss">

	body {
		margin: 0;
		padding: 0;
	}

	button {
		margin: 0;
		padding: 0;
		border: 0;
		background: none;
		font-size: 100%;
		vertical-align: baseline;
		font-family: inherit;
		font-weight: inherit;
		color: inherit;
		-webkit-appearance: none;
		appearance: none;
		-webkit-font-smoothing: antialiased;
		-moz-font-smoothing: antialiased;
		font-smoothing: antialiased;
	}

	body {
		font: 14px 'Helvetica Neue', Helvetica, Arial, sans-serif;
		line-height: 1.4em;
		background: #f5f5f5;
		color: #4d4d4d;
		min-width: 230px;
		max-width: 550px;
		margin: 0 auto;
		-webkit-font-smoothing: antialiased;
		-moz-font-smoothing: antialiased;
		font-smoothing: antialiased;
		font-weight: 300;
	}

	button,
	input[type="checkbox"] {
		outline: none;
	}

	.hidden {
		display: none;
	}

	.todoapp {
		background: #fff;
		margin: 130px 0 40px 0;
		position: relative;
		box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.2),
		0 25px 50px 0 rgba(0, 0, 0, 0.1);
	}

	label {
		margin: 0;
		padding: 0;
	}
</style>
