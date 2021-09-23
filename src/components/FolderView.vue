<template>
	<div class="folder" >
		<div class="folder__title" >
	
			<img class="folder__image" src="../img/folder.svg" alt="">
			<!-- <img class="folder__image" src="../img/folder.svg" alt=""> -->
			<p class="folder__name">{{name}}</p>
				
		</div>

		<template v-for="folder in folders">
			<FolderView v-bind:name="folder.name" v-bind:folders="folder.folders" v-bind:files="folder.files"/><!--  <----- РЕКУРСИЯ* -->
		</template>
	
		<template v-for = "file in files">
			<FileView v-bind:name = "file.name" v-bind:type = "file.type"/>
		</template>
	</div>
</template>

<script>
import FileView from "./FileView";
export default {
	name: 'FolderView',
	components: {FileView},
	props: {
		name: String,
		folders:Array,
		files:Array
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.folder{
	width: 500px;
	// margin: 0 auto;
	margin-bottom: 10px;
	color: rgb(255, 255, 255);
	text-decoration: none;
	// &:hover {
	// 	background: rgba(255, 255, 255, 0.233);
	// }
	&__title {
		display: flex;
		align-items: center;
		margin-bottom: 10px;
	}

	&__image {
		width: 50px;
		height: 50px;
	}

	&__name {
		margin-left: 5px;
	}

	.folder .file, .folder .folder {
		margin-left: 50px;
	}

}
</style>
