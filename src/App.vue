<template>
	<div id="app">
		<img alt="Vue logo" src="./assets/logo.png">
		<index />
	</div>
</template>

<script>
	import index from './pages/index_page.vue'

	export default {
		name: 'App',
		components: {
			index
		},
		methods() {
			
		}
	}
</script>

<style>
	#app {
		font-family: Avenir, Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		color: #2c3e50;
		margin-top: 60px;
	}
</style>
