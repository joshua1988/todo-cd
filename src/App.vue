<template>
  <div>
    <todo-header></todo-header>
    <todo-input v-on:add="addTodoItem"></todo-input>
    <!-- TODO: remove 버튼 구현해보세요 -->
    <todo-list 
      v-bind:items="todoItems"
      v-on:remove="removeTodoItems"
    ></todo-list>
    <todo-footer v-on:clear="clearTodoItems"></todo-footer>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue';
import TodoInput from './components/TodoInput.vue';
import TodoList from './components/TodoList.vue';
import TodoFooter from './components/TodoFooter.vue';

export default {
	components: {
		TodoHeader,
		// TodoInput: () => import('./components/TodoInput.vue'),
		TodoInput,
		TodoList,
		TodoFooter,
	},
	data() {
		return {
			todoItems: [],
		};
	},
	methods: {
		addTodoItem(value) {
			// debugger;
			this.todoItems.push(value);
			localStorage.setItem(value, value);
		},
		removeTodoItems(todoItem, index) {
			this.todoItems.splice(index, 1);
			localStorage.removeItem(todoItem);
		},
		fetchTodoItems() {
			for (var i = 0; i < localStorage.length; i++) {
				var item = localStorage.key(i);
				this.todoItems.push(item);
			}
		},
		clearTodoItems() {
			this.todoItems = [];
			localStorage.clear();
		},
	},
	created() {
		this.fetchTodoItems();
	},
};
</script>

<style>
</style>