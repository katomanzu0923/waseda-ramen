<template>
	<div class="ly">
		<div>
			<h2>About US</h2>
			<p>私たち早稲田大学ラーメン部は創立10年目を迎える大規模インカレラーメンサークルです。</p>
			<p>ラーメン好きな男子から、一人でラーメン屋にいけない女子でも大学生なら大丈夫！</p>
			<p>日本最大級の早稲田大学ラーメン部で大学生活を楽しみましょう!</p>
		</div>
		<h2>Q＆A</h2>
		<div class="bl_about">
			<h3>普段の活動内容は?</h3>
			<h4>基本的に一週間のうち平日の二日間夜の７時に都内のラーメン屋に集合して、ファミレスでおしゃべりを行い１０時解散となっています。</h4>
		</div>
		<div class="bl_about">
			<h3>男女比は?</h3>
			<h4>年度によって変わりますが、基本的には５：５となる年が多いです！女性でも幹事長として活躍しており、女性でも活躍しやすい環境です。</h4>
		</div>
		<div class="bl_about">
			<h3>早稲田大学以外でもうきませんか？</h3>
			<h4>早稲田大学の学生が軸として創立した背景から早稲田の学生が多いですが、現状都内から様々な学生が集まり、早稲田とそのほかの学生の割合は5:5となっています。</h4>
			<h4>また、女子大も多いので学校のサークルでは味わえない恋愛にも発展の可能性も！笑</h4>
		</div>
		<div class="bl_about">
			<h3>金銭的負担が心配です…？</h3>
			<h4>私たちのサークルは年会費を一切取らないサークルです。必要なのは参加日のラーメン屋の1000円札１枚！</h4>
			<h4>イベント等では都度、お金の支払いは発生しますが、全てのイベント自由参加なのでお財布と相談したサークルへの参画が可能となっています。</h4>
		</div>
		<div class="bl_about">
			<h3>ケンサーでも大丈夫ですか？</h3>
			<h4>兼サーでも問題ありません！行ける時に行く！これがラーメン部の良いところです笑</h4>
		</div>
	</div>
</template>

<script>
export default {
	data(){
		return{

		}
	}
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400&family=Potta+One&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Potta+One&display=swap');


$maincolor:#9B072D;
$maincolor_50:#9b072c85;
$subcolor:rgb(48, 48, 48);
$subcolor_50:rgba(48, 48, 48, 0.5);

h2{
	color: $maincolor;
	font-size: 30px;
	font-family: 'Potta One', cursive;
}

h3{
	color: $maincolor;
	padding: 1%;
	border-bottom: 1px $maincolor_50 solid;
	background: $subcolor;
	color: white;
}

h4{
	margin: 0;
	font-size: 20px;
	padding: 1%;
}

p{
	margin: 0;
	font-size: 20px;
	padding: 1%;
}

.ly{
	position: absolute;
	left: 10%;
	top: 0;
	width: 90%;
	text-align: center;
	font-family: 'Noto Sans JP', sans-serif;
}

.bl_about{
	margin: 2% 10%;
	box-shadow: rgba(116, 60, 60, 0.918) 0px 0.1em 0.1em, rgb(56, 31, 31) 0px 0.125em 1em,  $maincolor 0px 0px 0px 1px inset;
	width: 80%;
	color: white;
	background: $subcolor_50;
}




</style>