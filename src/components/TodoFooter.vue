<template>
  <div>
    <!-- TODO: 로컬 스토리지의 할 일 모두 지우기 구현 -->
    <button @click="clearAllItems">clear all</button>
  </div>
</template>

<script>
export default {
	methods: {
		clearAllItems: function() {
			// TODO: 화면의 할 일 목록을 어떻게 비울지 고민
			this.$emit('clear');
		},
	},
};
</script>

<style>
</style>