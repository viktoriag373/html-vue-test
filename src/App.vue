<template>
	<FolderView name=".." v-bind:folders="folders" v-bind:files="files" />
</template>

<script>
import FolderView from './components/FolderView.vue'
import data from './data/list';

export default {
  name: 'App',
  components: {
    FolderView
  },
  data: () => data
}
</script>

<style lang="scss">
* {
	margin: 0;
	padding: 0;	
	box-sizing: border-box;
}
body {
	font-size: 18px;
	#app {
		font-family: Avenir, Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		background: #252525;
		width: 100%;
		padding: 20px;
	}
}

</style>
