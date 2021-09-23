<template>
	<div class="file">
		<div class="file__title" >
			<img v-if = "type == 'image/svg'" class="file__image" src="../img/svg-1.svg" alt="">
			<img v-else-if = "type =='image/jpeg'" class="file__image" src="../img/jpg-1.svg" alt="">
			<img v-else-if = "type =='image/png'" class="file__image" src="../img/png-1.svg" alt="">
			<img v-else-if = "type =='application/octet-stream'" class="file__image" src="../img/text.svg" alt="">
			<img v-else-if = "type =='text/plain'" class="file__image" src="../img/text.svg" alt="">
			<img v-else-if = "type =='application/javascript'" class="file__image" src="../img/js-1.svg" alt="">
			<img v-else-if = "type =='application/json'" class="file__image" src="../img/json-1.svg" alt=""/>
			<img v-else class="file__image" src="../img/text.svg" alt="">
			<p class="file__name">{{name}}</p>
		</div>
	</div>
	
</template>

<script>
export default {
	name: 'FileView',
	props: {
		name: String,
		type: String
	}
}
</script>

<style scoped lang="scss">

.file {
	margin-bottom: 5px;
	&__title {
		display: flex;
		align-items: center;
	}

	&:hover {
		background: rgba(255, 255, 255, 0.233);
		cursor: pointer;
	}
	&__image {
		width: 50px;
		height: 50px;
	}

	&__name {
		transition: background 0.5s;
		color: rgb(255, 255, 255);
		margin-left: 5px;
	}
}
</style>
