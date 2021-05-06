<template>
	<div class="ly">
		<h1>過去の実績</h1>
		<div>
			<h2>2021~</h2>
			<div class="bl_body01">
				<div class="bl_body_cont">
					<h3>東京麺珍亭本舗様とコラボ商品</h3>
					<div class="img"><img :src="past2021_01"></div>
					<p>東京麺珍亭本舗様とコラボ商品を出しました。コロナ渦の中ラーメン各界を盛り上げようと企業様と最高のラーメンを出しました。</p>
				</div>
			</div>
		</div>
		<div>
			<h2>2020~</h2>
			<div class="bl_body01">
				<div class="bl_body_cont">
					<h3>すするTV出演</h3>
					<div class="img"><img :src="past2020_01"></div>
					<p>登録者数50万人を超えるラーメン系youtuberのすするTVに出演させていただきました。他大学と熾烈な戦いの末結果はいかに！！</p>
				</div>
			</div>
		</div>
		<div>
			<h2>2019~</h2>
			<div class="bl_body01">
				<div class="bl_body_cont">
					<h3>麺処ほん田さんとコラボ商品</h3>
					<div class="img"><img :src="past2019_01"></div>
					<p>麺処ほん田さんとコラボ商品を出しました。タレの味の吟味を重ね最高のラーメンを出店することができました。</p>
				</div>
				<div class="bl_body_cont">
					<h3>TOKYO BIG6 FESTIVAL 2019 supported by CHINTAIで優勝</h3>
					<div class="img"><img :src="past2019_02"></div>
					<p>TOKYO BIG6 FESTIVAL 2019 supported by CHINTAIというイベントにおいて参加しmした。ラーメンはもちろん他のグルメサークルとの競争は熾烈を極めましたが、無事優勝という結果を得ることができました。</p>
				</div>
			</div>
		</div>
		<div>
			<h2>~2018</h2>
			<div class="bl_body01">
				<div class="bl_body_cont">
					<h3>ラーメン燈郎さんとコラボ商品</h3>
					<div class="img"><img :src="past2018_01"></div>
					<p>ラーメン燈郎さんとコラボ商品を出しました。ラーメン燈郎さんと何度も試食を繰り返し、結果的にブロック優勝を果たしました!</p>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data(){
		return{
			a:1,
			Head_01: require('@/assets/takakura.png'),
			past2021_01: require('@/assets/2021_past01.png'),
			past2020_01: require('@/assets/past2020_01.png'),
			past2019_01: require('@/assets/past2019_01.png'),
			past2019_02: require('@/assets/past2019_02.png'),
			past2018_01: require('@/assets/past2018_01.png'),
		}
	}
}
</script>

<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400&family=Potta+One&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400&family=Potta+One&display=swap');
$maincolor:#9B072D;
$maincolor_50:#9b072c85;
$subcolor:rgb(48, 48, 48);
$subcolor_50:grey;

.ly{
	position: absolute;
	top: 0;
	left: 10%;
	width: 90%;
	font-family: 'Noto Sans JP', sans-serif;
}

h1{
	color: $maincolor;
	font-family: 'Potta One', cursive;
}

h3{
	color: white;
	background: $subcolor_50;
	margin: 0;
	padding: 0;
	padding-top: 5%;
}

p{
	color: white;
	border-top: 1px solid $subcolor;
	padding: 2%;
	text-align: start;
}

img{
	width: 100%;
}

.img{
	width: 90%;
	margin: 5% 5%;
}

.bl_body01{
	display: flex;
	justify-content: start;
	flex-wrap: wrap;
	width: 80%;
	margin: 0 10%;
}



.bl_body_cont{
	width: 30%;
	margin: 0 2%;
	background: $subcolor_50;
	box-shadow: $subcolor 0px 0.1em 0.1em, $subcolor 0px 0.125em 1em, $subcolor_50 0px 0px 0px 1px inset;
}

.bl_body01::after{
	content:"";
  display: block;
  width:30%;
}



</style>