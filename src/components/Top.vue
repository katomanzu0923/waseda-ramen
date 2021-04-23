<template>
	<div>
		{{a}}
		<img :src="popImg01">
	</div>
</template>

<script>
export default {
	data(){
		return{
			a:1,
			popImg01: require('@/assets/top.png'),
		}
	}
}
</script>