<template>
	<div class="ly">
		<div class="bl_top">
			<div class="bl_bl">
					<div class="left_up"><img :src="right_img"><div class="jiku">あなたの大学生活をラーメンを軸に</div></div>
			</div>
		</div>
		<div class="bl_top_cont">
			<p class="bl_top_ttl">代表挨拶</p>
			<div class="bl_top_conts">
				<h2 class="bl_top_cont_ttl">最高のラーメン体験を！</h2>
				<div class="flex">
					<div class="text">
						<p>初めまして、早稲田大学ラーメン部四代目幹事長の高倉です。</p>
						<p>私たちはラーメン部は早稲田祭、六大学優勝の大規模インカレラーメンサークルです。
							週に二回厳選されたラーメンを食べる活動に加えて、ラーメンにまつわるイベントを行っております。
						</p>
						<p>また、現在は十代目まで続くというしっかりとした歴史を持っています。ラーメンを食べにいく友だいが欲しい！人〜</p>
						<p>大学1年生から3年生までならどの大学でも大丈夫。みんなでおいしいラーメン屋へ行ききましょう！</p>
					</div>
					<div class="im">
						<img class="img02" :src="takaImg01">
						早稲田大学ラーメン部  四代目幹事長<br><p>高倉裕一郎</p>
					</div>
				</div>
			</div>
			<div></div>
		</div>
	</div>
</template>

<script>
export default {
	data(){
		return{
			a:1,
			
			popImg01: require('@/assets/top01.png'),
			takaImg01:require('@/assets/takakura.png'),
			current_slide: 1,
			left_img:require('@/assets/top02.png'),
			right_img:require('@/assets/top01.png'),
			left_up:[
				require('@/assets/top01.png'),
				require('@/assets/top02.png'),
			],
			right_up:[
				require('@/assets/top02.png'),
				require('@/assets/top01.png'),
			]
		}
	},
	mounted() {
		setInterval(() => {
			if(this.current_slide == 4)
			{
				this.current_slide = 1
				this.right_img = this.left_up[0]
			}
			else if(this.current_slide <4){
				this.current_slide +=1
				this.right_img = this.left_up[1]
			}
		}, 3000)
},


}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400&family=Potta+One&display=swap');

$maincolor:#9B072D;
$subcolor:rgb(119, 117, 117);

.ly{
	position: absolute;
	width: 90%;
	height: 90vh;
	left: 10%;
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
p{
	font-size: 20px;
	margin: 3% 0;
}
.text{
	text-align: center;
	width: 70%;
	vertical-align: middle;
	padding: 0 5%;
	height: 90%;
	color: white;
	font-family: 'Noto Sans JP', sans-serif;
}

.im{
	width: 30%;
	padding: 0 2.5% 5% 5%;
	color: white;
}

.img02{
	height: 90%;
}

.img{
}

.flex{
	display: flex;
	width: 100%;
}

h2{
	font-size: 16px;
	text-align: start;
}

h3{
	font-size: 24px;
}

.jiku{
	position: absolute;
  top: 40%;
  left: 0;
  right: 0;
  bottom: 0;
  margin: auto;
	color: red;
	font-size: 50px;
}

.bl_top{
	width: 100%;
}


.bl_bl{
	position: relative;
	display: flex;
	flex-direction: wrap;
	margin: 0;
	height: 100vh;
}

.bl_top_cont{
	text-align: center;
	width: 80%;
	margin: 0 10%;
}

.bl_top_ttl{
	font-size: 26px;
	color: $maincolor;
}
.bl_top_conts{
	color: $maincolor;
	background: $subcolor;
	box-shadow: rgba(116, 60, 60, 0.918) 0px 0.1em 0.1em, rgb(56, 31, 31) 0px 0.125em 1em,  $maincolor 0px 0px 0px 1px inset;
}

.img_50{
	opacity: 50%;
}

.img_100{
	opacity: 100%;
}

.bl_top_left{
	width: 30%;
	border-right: 2px solid beige;
	padding: 2% 0;
}

.bl_top_right{
	width: 60%;
}

.bl_top_cont_ttl{
	text-align: start;
	font-weight: 200;
	border-bottom: 1px solid red;
	width: 90%;
	font-size: 40px;
	margin: 2% 5%;
	padding: 1% 0 10px 2%;
}

.bl_top_txt{
	width: 80%;
	margin: 0 10%;
}

img{
	width: 100%;
	height: 100%;
}

.img{
	height: 50%;
	width: 50%;
	margin: 0 25%;
	padding: 0 2%;
}
.left_up{
	width: 100%;
	top: 0;
	left: 0;
}

.aa{
	display: block;
	background: yellow;
}

.bl_sub_cont{
	text-align: center;
	width: 80%;
	margin: 0 10%;
}

.sub{
	display: flex;
	justify-content: space-evenly;
	width: 100%;
}

.sub01{
	background: red;
}

.sub02{
}

</style>