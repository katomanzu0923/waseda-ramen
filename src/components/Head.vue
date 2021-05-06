
<template>
	<div class="ly">
		<h1>現ラーメン部の幹部の紹介</h1>
		<div>
			<div class="top01">
				<div class="img"><img :src="Head_01"></div>
				<h2 class="sub_text00">四代目幹事長</h2>
				<h2 class="name">高倉裕一郎</h2>
				<div class="subtop01">
					<div class="left">
						<h2 class="sub_text02">早稲田大学</h2>
						<h4>社会科学部</h4>
					</div>
					<div class="right">
						<h2 class="sub_text02">好きなラーメン屋</h2>
						<h2>麺屋  一灯</h2>
					</div>
				</div>
			</div>
			<div class="sub">
				<div class="top02">
					<div class="img">
						<img :src="Head_02">
					</div>
					<h2 class="sub_text00">四代目副幹事長</h2>
					<h2>鈴木春香</h2>
					<div class="subtop01">
						<div class="left">
							<h2 class="sub_text02">共立女子大学</h2>
							<h4>国際学部</h4>
						</div>
						<div class="right">
							<h2 class="sub_text02">好きなラーメン屋</h2>
							<h2>篝</h2>
						</div>
					</div>
				</div>
				<div class="top02">
					<div class="img">
						<img :src="Head_03">
					</div>
					<h2 class="sub_text00">四代目副幹事長</h2>
					<h2>堀越拓海</h2>
					<div class="subtop01">
						<div class="left">
							<h2 class="sub_text02">早稲田大学</h2>
							<h4>人間科学部</h4>
						</div>
						<div class="right">
							<h2 class="sub_text02">好きなラーメン屋</h2>
							<h2>パパパパイン</h2>
						</div>
					</div>
				</div>
				<div class="top02">
					<div class="img">
						<img :src="Head_04">
					</div>
						<h2 class="sub_text00">四代目広報</h2>
						<h2>加藤貴大</h2>
					<div class="subtop01">
						<div class="left">
							<h2 class="sub_text02">同志社大学</h2><h4>法学部</h4>
						</div>
						<div class="right">
							<h2 class="sub_text02">好きなラーメン屋</h2><h2>海神</h2>
						</div>
					</div>
				</div>
				<div class="top02">
					<div class="img"><img :src="Head_05"></div>
					<h2 class="sub_text00">四代目広報</h2>
					<h2>光永智哉</h2>
					<div class="subtop01">
						<div class="left">
							<h2 class="sub_text02">法政大学</h2><h4>デザイン学部</h4>
						</div>
						<div class="right">
							<h2 class="sub_text02">好きなラーメン屋</h2><h2>BASSO</h2>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data(){
		return{
			Head_01: require('@/assets/takakura.png'),
			Head_02: require('@/assets/harutyan01.png'),
			Head_03: require('@/assets/horikosi.png'),
			Head_04: require('@/assets/kato.png'),
			Head_05: require('@/assets/mitunaga.png'),
		}
	}
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400&family=Potta+One&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400&family=Potta+One&display=swap');
$maincolor:#9B072D;
$maincolor_50:#ec7c9886;
$subcolor:rgb(48, 48, 48);
$subcolor_50:rgba(48, 48, 48, 0.5);

h1{
	color: $maincolor;
	font-family: 'Potta One', cursive;
}
h2{
	margin: 5% 0;
	color: white;
}

h4{
	font-size: 20px;
	margin: 5%;
	color: white;
}

.name{
	color: white;
}

.top01{
	background: $subcolor_50;
	width: 40%;
	margin: 5% 30%;
	color: white;
}

.top02{
	background: $subcolor_50;
	width: 40%;
	margin: 5% 30%;
	color: white;
}

.submtop01{
	display: flex;
	background:$subcolor_50;
	margin: 0;
	box-shadow: $subcolor_50 0px 0.1em 0.1em,$subcolor_50 0px 0.125em 1em, $subcolor_50 0px 0px 0px 1px inset;
}

.subtop01 {
	display: flex;
	margin: 0;
	box-shadow: $subcolor_50 0px 0.1em 0.1em,$subcolor_50 0px 0.125em 1em, $subcolor_50 0px 0px 0px 1px inset;
}
.img{
	display: inline-block;
}
.img{
	width: 100%;
}
img{
	margin: 2% 30%;
	border-radius: 50%;  
	width: 40%;
	height: 100%;

}

.left{
	width: 50%;
}

.right{
	width: 50%;
	border-left: dotted $subcolor_50 2px;
}

.sub_text00{
	margin: 1%;
	text-align: center;
	font-size: 14px;
	color: white;
}

.sub_text01{
	margin: 0;
	text-align: start;
	font-size: 14px;
	color: royalblue;
	padding: 5% 0 0 5%;
}

.sub_text02{
	margin: 5%;
	text-align: start;
	font-size: 14px;
	padding: 0;
	color: white;
}


.sub{
	display: flex;
	flex-wrap:wrap;
	justify-content: space-evenly;
	width: 100%;
	color: white;
	margin: 5% 0;
}

.sub:after {
    content: "";
    display: block;
    width: 59%; 
	}

.top02{
	color: white;
	background: $subcolor_50;
	width: 25%;
	margin: 2.5% 1%;
	box-shadow: $subcolor_50 0px 0.1em 0.1em,$subcolor_50 0px 0.125em 1em, $subcolor_50 0px 0px 0px 1px inset;
}

.ly{
	position: absolute;
	left: 10%;
	width: 90%;
	font-family: 'Noto Sans JP', sans-serif;
}
</style>