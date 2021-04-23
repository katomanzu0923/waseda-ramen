<template>
  <div class="ly">
		<p>logo</p>
		<transition>
			<div class="upmenu" v-if="updata">
				<p class="bl_cls" @click="close()">✖︎</p>
				<p>-MENU-</p>
				<div>
					<p @click="up(1)">Top</p>
					<p @click="up(2)">ラーメン部について</p>
					<p @click="up(3)">年間予定</p>
					<p @click="up(4)">幹部の紹介</p>
					<p @click="up(5)">企業の方へ</p>
				</div>
			</div>
		</transition>
			<p class="hum" @click="open()">triger</p>
	</div>
</template>

<script>
export default {
	data(){
    return{
			updata:false
    }
  },
	methods:{
		open(){
			this.updata = true
		},
		close(){
			this.updata = false
		},
		up(headNum){
			if(headNum == 1){
				this.$emit('change01')
				this.updata = false
			}
			else if(headNum == 2){
				this.$emit('change02')
				this.updata = false
			}
			else if(headNum == 3){
				this.$emit('change03')
				this.updata = false
			}
			else if(headNum == 4){
				this.$emit('change04')
				this.updata = false
			}
			else if(headNum == 5){
				this.$emit('change05')
				this.updata = false
			}
		}
	}
}
</script>

<style lang="scss" scoped>
$maincolor:#9B072D;
$subcolor:#777777;

.ly{

	position: absolute;
	left: 0;
	top: 0;
	width: 100%;
	background: $subcolor;
}

.hum{
	position: absolute;
	right: 5%;
}

.upmenu{
	position: absolute;
	left: 0;
	top: 0;
	background: $maincolor;
	width: 100%;
	height: 100vh;
	color: white;
}

.bl_cls{
	position: absolute;
	right: 5%;
	top: 0%;
	background: $subcolor;
}
</style>