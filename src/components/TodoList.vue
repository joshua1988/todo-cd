<template>
  <div>
    <ul>
      <li 
        v-for="(todoItem, index) in items"
        v-bind:key="index"
      >
        {{ todoItem }}
        <button v-on:click="removeTodoItem(todoItem, index)">
          remove
        </button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
	// 인스턴스 옵션 속성
	props: ['items'],
	methods: {
		removeTodoItem(todoItem, index) {
			this.$emit('remove', todoItem, index);
		},
	},
};
</script>

<style>
</style>