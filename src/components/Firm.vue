<template>
	<div class="ly">
		<div>
			<h1>企業の方へ</h1>
			<p>私たち早稲田大学ラーメン部はラーメンの魅力を広げるために活動をしております。文化祭や各種ラーメンに関わるイベントに多くの企業の方と協力して参加をしてまいりました。もし、何か協力する点がありましたら、以下のフォームよりご連絡お願いします。</p>
			<div class="bl_form">
				<h2>入力フォーム</h2>
				<div>
					<div>
						<h3>企業名</h3>
						<input type="text" placeholder="株式会社ラーメン部" v-model="name">
					</div>
					<div>
						<h3>メールアドレス</h3>
						<input type="text" placeholder="wasedaramen@ne.jp" v-model="name">
					</div>
					<div>
						<h3>電話番号</h3>
						<input type="text" placeholder="03-3333-3333" v-model="name">
					</div>
					<div>
						<h3>ご用件</h3>
						<textarea type="text" v-model="name" rows="10" placeholder="コラボしたいので、都合が合えばご返信お願いします"></textarea>
					</div>
					<button @click="sub()">送信</button>
				</div>
			</div>
		</div>
	</div>
</template>

<script>

export default {
	data(){
		return{
			popImg01: require('@/assets/twi.png'),
			popImg02: require('@/assets/ling@2x.png'),
			popImg03: require('@/assets/insta.png'),
			up_num:0
		}
	},
	methods:{
		alert(){
			alert('f')
		},
		Up(num){
			if(num == 1){
				this.up_num = 1
			}
			else if(num == 2)
			{
				this.up_num = 2
			}
		},
		del(){
			this.up_num = 0
		},
		sub(){
			this.up_num = 0
		}
	}
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400&family=Potta+One&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400&family=Potta+One&display=swap');
$maincolor:#9B072D;
$maincolor_50:#9b072c85;
$subcolor:rgb(48, 48, 48);
$subcolor_50:grey;
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



.bl_box{
}

input{
	outline: none;
}

textarea{
	outline: none;
	width:500px;
}

p{
	width: 70%;
	margin: 0 15%;
}

h1{
	font-family: 'Potta One', cursive;
	color: $maincolor;
}

h2{
	font-size: 30px;
	color: $maincolor;
	padding-top: 2%;
}

h3{
	margin: 0;
	padding-bottom: 5px;
	padding-top: 1%;
}

h4{
	margin: 1% 5%;
	text-align: center;
	color: white;
	background: $maincolor;
}

img{
	width: 100%;
}

.line{
	width: 5%;
	margin: 0 47.5%;
	background: $maincolor;
}

.del{
	margin: 1%;
	position: absolute;
	top: 0;
	right: 0;
	color: white;
}

.bl_list{
	margin: 2% 0;
	width: 100%;
}

.bl_form{
	margin: 5% 10% 0;
	background: $subcolor_50;
	width: 80%;
	box-shadow: $subcolor_50 0px 0.1em 0.1em,$subcolor_50 0px 0.125em 1em, $subcolor_50 0px 0px 0px 1px inset;
}

button{
	margin: 1%;
	background: $maincolor;
	color: white;
	padding: 1% 5%;
}

.ly{
	position: absolute;
	left: 10%;
	width: 90%;
	font-family: 'Noto Sans JP', sans-serif;
}


</style>