<template>
	<div class="ly">
		<h1>過去の実績</h1>
		kari
		{{a}}
	</div>
</template>

<script>
export default {
	data(){
		return{
			a:1
		}
	}
}
</script>

<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400&family=Potta+One&display=swap');
$maincolor:#9B072D;
$maincolor_50:#9b072c85;
$subcolor:rgb(48, 48, 48);
$subcolor_50:rgba(48, 48, 48, 0.5);

.ly{
	position: absolute;
	top: 0;
	left: 10%;
	width: 90%;
}

h1{
	color: $maincolor;
}

.bl_body01{
	display: flex;
	justify-content: space-evenly;
}

.bl_body01{
	background: $subcolor;
	color: red;
}


</style>