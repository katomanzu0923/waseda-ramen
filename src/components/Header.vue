<template>
  <div class="ly">
		<div>
			<div class="nav_cont_pc">
				<div class="cont_pc">
					<div class="top_btn" @click="up(0)" v-on:mouseover="hoveOve(0)" v-on:mouseleave="hoveLea(0)" :class='{img_50:selected,img_100:select}'><img :src="popImg01"></div>
					<p @click="up(1)" v-on:mouseover="hoveOve(1)" v-on:mouseleave="hoveLea(1)" :class='{blue:selected01, red:stopC01}'>ラーメン部とは</p>
					<p @click="up(2)" v-on:mouseover="hoveOve(2)" v-on:mouseleave="hoveLea(2)" :class='{blue:selected02, red:stopC02}'>年間予定</p>
					<p @click="up(3)" v-on:mouseover="hoveOve(3)" v-on:mouseleave="hoveLea(3)" :class='{blue:selected03, red:stopC03}'>幹部の紹介</p>
					<p @click="up(4)" v-on:mouseover="hoveOve(4)" v-on:mouseleave="hoveLea(4)" :class='{blue:selected04, red:stopC04}'>過去の実績</p>
					<p @click="up(5)" v-on:mouseover="hoveOve(5)" v-on:mouseleave="hoveLea(5)" :class='{blue:selected05, red:stopC05}'>企業の方へ</p>
					<p @click="up(6)" v-on:mouseover="hoveOve(6)" v-on:mouseleave="hoveLea(6)" :class='{blue:selected06, red:stopC06}'>参加希望の方へ</p>最新情報は下記から
					<div :class='{imgb:selected07}' v-on:mouseover="hoveOve(7)" v-on:mouseleave="hoveLea(7)"><div class="img01"><img :src="popImg02" ></div><h6>Twitter</h6></div>
					<div :class='{imgb:selected08}' v-on:mouseover="hoveOve(8)" v-on:mouseleave="hoveLea(8)"><div class="img02"><img :src="popImg03" ></div><h6>Instagram</h6></div>
				</div>
				</div>
		</div>
		<div class="none">
			<div class="hamburger_btn" @click="active()">
      <span class="line line_01" :class="{'btn_line01':ActiveBtn}"></span>
      <span class="line line_02" :class="{'btn_line02':ActiveBtn}"></span>
      <span class="line line_03" :class="{'btn_line03':ActiveBtn}"></span>
			</div>
			<transition name="fade">
			<div class="upmenu" v-if="updata">
				<h1>-  MENU  -</h1>
				<div class="nav_cont">
					<p @click="up(1)">Top</p>
					<p @click="up(2)">ラーメン部について</p>
					<p @click="up(3)">年間予定</p>
					<p @click="up(4)">幹部の紹介</p>
					<p @click="up(5)">企業の方へ</p>
					<p @click="up(4)">幹部の紹介</p>
					<p @click="up(5)">企業の方へ</p>
				</div>
			</div>
			</transition>
		</div>
  </div>
</template>

<script>
export default {
	data(){
    return{
			updata:false,
			selected:false,
			select:true,
			stopC:false,
			stopC01:false,
			stopC02:false,
			stopC03:false,
			stopC04:false,
			stopC05:false,
			stopC06:false,
			ActiveBtn: false,
			selected01:false,
			selected02:false,
			selected03:false,
			selected04:false,
			selected05:false,
			selected06:false,
			selected07:false,
			selected08:false,
			popImg01: require('@/assets/wasedaramen_logo05.png'),
			popImg02: require('@/assets/twi.png'),
			popImg03: require('@/assets/insta.png'),
    }
  },
	methods:{
		home(){
			this.$emit('change01')
			this.updata = false
		},
		hoveOve(num){
			if(num == 0)
			{
				this.selected = true
				this.select = false
			}
			else if(num == 1)
			{
				this.stopC01 = true
			}
			else if(num == 2)
			{
				this.stopC02 = true
			}
			else if(num == 3)
			{
				this.stopC03 = true
			}
			else if(num == 4)
			{
				this.stopC04 = true
			}
			else if(num == 5)
			{
				this.stopC05 = true
			}
			else if(num == 6)
			{
				this.stopC06 = true
			}
			else if(num == 7)
			{
				this.selected07 = true
			}
			else if(num == 8)
			{
				this.selected08 = true
			}
		},
		hoveLea(num){
			if(num == 0)
			{
				this.selected = false
				this.select = true
			}
			else if(num == 1)
			{
				this.stopC01 = false
			}
			else if(num == 2)
			{
				this.stopC02 = false
			}
			else if(num == 3)
			{
				this.stopC03 = false
			}
			else if(num == 4)
			{
				this.stopC04 = false
			}
			else if(num == 5)
			{
				this.stopC05 = false
			}
			else if(num == 6)
			{
				this.stopC06 = false
			}
			else if(num == 7)
			{
				this.selected07 = false
			}
			else if(num == 8)
			{
				this.selected08 = false
			}
		},
		active(){
			if(this.ActiveBtn == false){
				this.ActiveBtn = true
				this.updata = true
			}
			else if(this.ActiveBtn == true)
			{
				this.ActiveBtn  = false
				this.updata = false
			}
		},
		close(){
			this.updata = false
			this.ActiveBtn = false
		},
		up(headNum){
			if(headNum == 0){
				this.$emit('change00')
				this.updata = false
				if(this.stopC == true){
					this.stopC = false
				}
				else
				{
					this.stopC = true
				}
			}
			else if(headNum == 1){
				this.$emit('change01')
				this.updata = false
				this.selected01 = true
				this.selected02 = false
				this.selected03 = false
				this.selected04 = false
				this.selected05 = false
				this.selected06 = false
			}
			else if(headNum == 2){
				this.$emit('change02')
				this.updata = false
				this.selected01 = false
				this.selected02 = true
				this.selected03 = false
				this.selected04 = false
				this.selected05 = false
				this.selected06 = false
			}
			else if(headNum == 3){
				this.$emit('change03')
				this.updata = false
				this.selected01 = false
				this.selected02 = false
				this.selected03 = true
				this.selected04 = false
				this.selected05 = false
				this.selected06 = false
			}
			else if(headNum == 4){
				this.$emit('change04')
				this.updata = false
				this.selected01 = false
				this.selected02 = false
				this.selected03 = false
				this.selected04 = true
				this.selected05 = false
				this.selected06 = false
			}
			else if(headNum == 5){
				this.$emit('change05')
				this.updata = false
				this.selected01 = false
				this.selected02 = false
				this.selected03 = false
				this.selected04 = false
				this.selected05 = true
				this.selected06 = false
			}
			else if(headNum == 6){
				this.$emit('change06')
				this.updata = false
				this.selected01 = false
				this.selected02 = false
				this.selected03 = false
				this.selected04 = false
				this.selected05 = false
				this.selected06 = true
			}
		}
	}
}
</script>

<style lang="scss" scoped>
$maincolor:#9B072D;
$subcolor:rgb(48, 48, 48);
$subcolor_50:rgba(48, 48, 48, 0.5);

.red{
	background: $maincolor;
	color: white;
}

.blue{
	background: $maincolor;
	color: white;
	border-top: 3px solid white;
	border-bottom: 3px solid white;
}

.fade-enter-active,.fade-leave-active {
  transition: all 0.5s ease;
}
.fade-enter {
	opacity: 0;
}
.fade-enter-to{
	opacity: 1;
}
.fade-leave{
  opacity: 1;
}
.fade-leave-to {
	opacity: 0;
}
.img{
	display: flex;
	justify-content: space-evenly;
}

.img_50{
	opacity: 50%;
}

.img_100{
	opacity: 100%;
}

p{
	font-size: 20px;
	color: $maincolor;
	padding: 10% 0;
	background: rgb(219, 219, 219);
	width: 100%;
	border-bottom: $maincolor 2px solid;
	border-top: $maincolor 2px solid;
}


.nav_cont_pc{
	position: absolute;
	background:$subcolor;
	width: 10%;
	height: 250vh;
	left: 0;
	top: 0;
	z-index: 10;
}

.logo{
	width: 100%;
	padding: 1% 0;
	background: rgba(160, 63, 63, 0.514);
}

.cont_pc{
	position: fixed;
	width: 10%;
}

.top_btn{
	width: 80%;
	margin: 0 10%;
}

img{
	width: 100%;
}

.img01{	
	width: 10%;
	padding-left: 45%;
	margin: 5% 0;
}

.imgb{
	background: $maincolor;
	margin: 5% 0;
}

.img02{	
	width: 10%;
	padding-left: 45%;
	margin: 5% 0;
}

h6{
	margin: 0;
}

p{
	margin: 20% 0;
}

.none{
	display: none;
}

.hamburger_btn {
  position: fixed; /*常に最上部に表示したいので固定*/
  top: 0;
  right: 0;
  width: 70px;
  height: 72px;
  cursor: pointer;
  z-index: 50;
}

.hamburger_btn .line {
  position: absolute;
  top: 0;
  left: 20px;
  width: 32px;
  height: 3px;
  background:white;
  text-align: center;
	z-index: 2;
}

.hamburger_btn .line_01 {
  top: 16px;
  transition: 0.4s ease;
}
.hamburger_btn .line_02 {
  top: 26px;
  transition: 0.4s ease;
}
.hamburger_btn .line_03 {
  top: 36px;
  transition: 0.4s ease;
}
.line_04 {
  top: 46px;
  transition: 0.4s ease;
}


.btn_line01 {
  transform: translateY(10px) rotate(-45deg);
  transition: 0.4s ease;
}
.btn_line02 {
  transition: 0.4s ease;
  opacity: 0;
}
.btn_line03 {
  transform: translateY(-10px) rotate(45deg);
  transition: 0.4s ease;
}
.ly{
	position: absolute;
	left: 0;
	top: 0;
	width: 100%;
	background: rgba(128, 128, 128, 0.219);
	color:white;
	z-index: 10;
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

.nav_cont{
	margin: 5% 0;
}

.img{
	margin: 5% 0;
}
</style>