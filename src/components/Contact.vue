<template>
	<div class="ly">
		<transition name="fade">
			<div v-if="up_num == 1" class="mod">
				<p class="del" @click="del()">✖︎</p>
				<h1>私たち早稲田大学ラーメン部はラーメンの魅力を広げるために活動をしております。文化祭や各種ラーメンに関わるイベントに多くの企業の方と協力して参加をしてまいりました。もし、何か協力する点がありましたら、以下のフォームよりご連絡お願いします。</h1>
				<p>Form</p>
				<div>
					<div>
						<h3>企業名</h3>
						<input type="text" v-model="name">
					</div>
					<div>
						<h3>企業名</h3>
						<input type="text" v-model="name">
					</div>
					<div>
						<h3>企業名</h3>
						<textarea type="text" v-model="name"></textarea>
					</div>
					<button @click="sub()">送信</button>
				</div>
			</div>
			<div v-if="up_num == 2" class="mod">
				<p class="del" @click="del()">✖︎</p>
				<h1>kari</h1>
				<p>Form</p>
				<div>
					<div>
						<h3>企業名</h3>
						<input type="text" v-model="name">
					</div>
					<div>
						<h3>企業名</h3>
						<input type="text" v-model="name">
					</div>
					<div>
						<h3>企業名</h3>
						<textarea type="text" v-model="name"></textarea>
					</div>
					<button @click="sub()">送信</button>
				</div>
			</div>
		</transition>
		<div>
			<h1>参加希望の方へ</h1>
			<h2>
				早稲田大学ラーメン部に加入のご検討ありがとうございます。<br>
				私たち早稲田大学ラーメン部に関しましては入部に関していくつかの条件があります。<br>
				<div class="bl_list">
					<h3>加入条件</h3>
					<li>大学１.2年生もしくは専門学校1年生であること（どこの大学かは問いません！）</li>
					<li>危険な飲酒行為を行わないこと(私たちのサークルでは<span>コール</span>などは厳禁としております)</li>
				</div>
				<h4>以上この２点の条件を承諾される方は以下のリンクより公式ラインにてご連絡ください！</h4>
			</h2>
			<div class="bl_box">
				<div class="line"  @click="alert()">
					<img :src="popImg02">
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
$subcolor_50:rgba(128, 127, 127, 0.486);
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

li{
	text-align: start;
}

li span{
	border-bottom: 3px solid $maincolor;
}

p{
	width: 30%;
	background: $maincolor;
	margin: 1% 5%;
}

h1{
	font-family: 'Potta One', cursive;
	color: $maincolor;
}

h2{
	text-align: center;
}

h3{
	padding: 5px 0;
	margin: 0 35%; 
	width: 30%;
}

h4{
	text-align: center;
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
	margin: 2% 10%;
	width: 80%;
	border: 2px solid red;
	padding: 2%;
	background: $subcolor_50;
	box-shadow: $subcolor_50 0px 0.1em 0.1em,$subcolor_50 0px 0.125em 1em, $subcolor_50 0px 0px 0px 1px inset;
}

.ly{
	position: absolute;
	left: 10%;
	width: 90%;
	font-family: 'Noto Sans JP', sans-serif;
}


</style>