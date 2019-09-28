<template>
  <div>
    <input 
      type="text" 
      v-model="inputText"
      v-on:keyup.enter="addTodo"
    >
    <button v-on:click="addTodo">add</button>
  </div>
</template>

<script>
export default {
	data: function() {
		return {
			inputText: '',
		};
	},
	methods: {
		addTodo: function() {
			// if (event.keyCode === 13) {
			// 	console.log('입력');
			// }
			// console.log(event);
			var value = this.inputText;
			this.$emit('add', value);
			this.clearInput();
		},
		clearInput: function() {
			// console.log(this);
			this.inputText = '';
		},
	},
};
</script>

<style>
</style>