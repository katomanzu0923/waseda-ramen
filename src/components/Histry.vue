<template>
<div class="ly">
	<transition name="fade">
			<div class="up_bl" v-if="up_num">
				<p class="del" @click="del()">✖︎</p>
				<h5>{{ttlCont}}</h5>
				<div class="bu">
					<div class="ig"><img :src="popImg01"></div><div class="ig"><img :src="popImg02"></div><div class="ig"><img :src="popImg03"></div>
				</div>
				<div class="up_cont">
					<div class="left">
						<p>活動内容</p>
						<div>
							<h3>何やるの？</h3>
							<p>{{cont}}</p>
						</div>
						<div>
							<h3>時期は?</h3>
							<p>{{dayCont}}</p>
						</div>
						<div>
							<h3>場所は</h3>
							<p>{{areaCont}}</p>
						</div>
						<div>
							<h3>予算は</h3>
							<p>{{moneyCont}}</p>
						</div>
					</div>
					<div class="right">
						<p>参加者の声</p>
						<div>
							<div class="popImg-size">
								<img  class="popImg" :src="human">
							</div>
							<p>{{exCont01}}</p>
						</div>
						<div>
							<div class="popImg-size">
								<img  class="popImg" :src="human">
							</div>
							<p>{{exCont02}}</p>
						</div>
					</div>
				</div>
			</div>
	</transition>
	<div :class="[up_num? 'js':'def']">
		<h1>年間予定</h1>
		<div class="top">
			<div class="zenki" @click="change(1)" :class="[out !==1? 'el_btn_is':'el_btn_def']" v-on:mouseover="acin()" v-on:mouseleave="acout()"><p :class="{ 'defblue': selected02, 'blue': selected01 }">前期</p></div>
			<div class="koki" @click="change(2)" :class="[out !==1? 'el_btn_def':'el_btn_is']" v-on:mouseover="acin01()" v-on:mouseleave="acout01()"><p :class="{ 'defblue': selected03, 'blue': selected04 }">後期</p></div>
		</div>
		<transition name="fade">
			<div v-if="out == 2" class="cont">
				<div class="cont_cont01">
					<p class="m">4<span>月</span></p>
					<div class="card01">
						<h2>新歓活動</h2>
						<div class="img02"><img  :src="Img00"></div>
						<h4 @click="up(0)" v-on:mouseover="btnOver(0)" v-on:mouseleave="btnLeave(0)" :class="{ 'defbtn': btn00, 'jsbtn': btn00Is }">詳細</h4>
					</div>
				</div>
				<div class="cont_cont02">
					<p class="m">5<span>月</span></p>
					<div class="card01">
						<h2>BBQ</h2>
						<div class="img02"><img  :src="Img01"></div>
						<h4 @click="up(1)" v-on:mouseover="btnOver(1)" v-on:mouseleave="btnLeave(1)" :class="{ 'defbtn': btn01, 'jsbtn': btn01Is }">詳細</h4>
					</div>
					<div class="card01">
						<h2>横浜イベント</h2>
						<div class="img02"><img  :src="Img02"></div>
						<h4 @click="up(2)" v-on:mouseover="btnOver(2)" v-on:mouseleave="btnLeave(2)" :class="{ 'defbtn': btn02, 'jsbtn': btn02Is }">詳細</h4>
					</div>
				</div>
				<div class="cont_cont02">
					<p class="m">6<span>月</span></p>
					<div class="card01">
						<h2>ディズニー</h2>
						<div class="img02"><img  :src="Img03"></div>
						<h4 @click="up(3)" v-on:mouseover="btnOver(3)" v-on:mouseleave="btnLeave(3)" :class="{ 'defbtn': btn03, 'jsbtn': btn03Is }">詳細</h4>
					</div>
					<div class="card01">
						<h2>新歓合宿</h2>
						<div class="img02"><img  :src="Img04"></div>
						<h4 @click="up(4)" v-on:mouseover="btnOver(4)" v-on:mouseleave="btnLeave(4)" :class="{ 'defbtn': btn04, 'jsbtn': btn04Is }">詳細</h4>
					</div>
				</div>
				<div class="cont_cont02">
					<p class="m">7<span>月</span></p>
					<div class="card01">
						<h2>テスト期間</h2>
						<div class="img02"><img  :src="Img01"></div>
						<h4 class="btn_test">ラーメンは我慢...</h4>
					</div>
				</div>
				<div class="cont_cont02">
					<p class="m">8<span>月</span></p>
					<div class="card01">
						<h2>海合宿</h2>
						<div class="img02"><img  :src="Img05"></div>
						<h4 @click="up(5)" v-on:mouseover="btnOver(5)" v-on:mouseleave="btnLeave(5)" :class="{ 'defbtn': btn05, 'jsbtn': btn05Is }">詳細</h4>
					</div>
					<div class="card01">
						<h2>幹部最終活動</h2>
						<div class="img02"><img  :src="Img06"></div>
						<h4 @click="up(6)" v-on:mouseover="btnOver(6)" v-on:mouseleave="btnLeave(6)" :class="{ 'defbtn': btn06, 'jsbtn': btn06Is }">詳細</h4>
					</div>
				</div>
				<div class="cont_cont02">
					<p class="m">9<span>月</span></p>
					<div class="card01">
						<h2>夏合宿</h2>
						<div class="img02"><img  :src="Img07"></div>
						<h4 @click="up(7)" v-on:mouseover="btnOver(7)" v-on:mouseleave="btnLeave(7)" :class="{ 'defbtn': btn07, 'jsbtn': btn07Is }">詳細</h4>
					</div>
				</div>
			</div>
			<div v-if="out == 1" class="cont">
				<div class="cont_cont02">
					<p class="m">10<span>月</span></p>
					<div class="card01">
						<h2>所沢祭</h2>
						<div class="img02"><img  :src="Img08"></div>
						<h4 @click="up(8)" v-on:mouseover="btnOver(8)" v-on:mouseleave="btnLeave(8)" :class="{ 'defbtn': btn08, 'jsbtn': btn08Is }">詳細</h4>
					</div>
				</div>
				<div class="cont_cont02">
					<p class="m">11<span>月</span></p>
					<div class="card01">
						<h2>早稲田祭</h2>
						<div class="img02"><img  :src="Img09"></div>
						<h4 @click="up(9)" v-on:mouseover="btnOver(9)" v-on:mouseleave="btnLeave(9)" :class="{ 'defbtn': btn09, 'jsbtn': btn09Is }">詳細</h4>
					</div>
				</div>
				<div class="cont_cont02">
					<p class="m">12<span>月</span></p>
					<div class="card01">
						<h2>クリパ</h2>
						<div class="img02"><img  :src="Img010"></div>
						<h4 @click="up(10)" v-on:mouseover="btnOver(10)" v-on:mouseleave="btnLeave(10)" :class="{ 'defbtn': btn010, 'jsbtn': btn010Is }">詳細</h4>
					</div>
				</div>
				<div class="cont_cont02">
					<p class="m">1<span>月</span></p>
					<div class="card01">
						<h2>テスト期間</h2>
						<div class="img02"><img  :src="Img01"></div>
						<h4 class="btn_test">ラーメンは我慢...</h4>
					</div>
				</div>
				<div class="cont_cont02">
					<p class="m">2<span>月</span></p>
					<div class="card01">
						<h2>ラーメン屋飲み会</h2>
						<div class="img02"><img  :src="Img011"></div>
						<h4 @click="up(11)" v-on:mouseover="btnOver(11)" v-on:mouseleave="btnLeave(11)" :class="{ 'defbtn': btn011, 'jsbtn': btn011Is }">詳細</h4>
					</div>
				</div>
				<div class="cont_cont02">
					<p class="m">3<span>月</span></p>
					<div class="card01">
						<h2>春合宿</h2>
						<div class="img02"><img  :src="Img012"></div>
						<h4 @click="up(12)" v-on:mouseover="btnOver(12)" v-on:mouseleave="btnLeave(12)" :class="{ 'defbtn': btn012, 'jsbtn': btn012Is }">詳細</h4>
					</div>
					<div class="card01">
						<h2>追いコン</h2>
						<div class="img02"><img  :src="Img013"></div>
						<h4 @click="up(13)" v-on:mouseover="btnOver(13)" v-on:mouseleave="btnLeave(13)" :class="{ 'defbtn': btn013, 'jsbtn': btn013Is }">詳細</h4>
					</div>
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
			stop:true,
			out:2,
			selected01:true,
			selected02:false,
			selected03:true,
			selected04:false,
			selected05:true,
			btn00:true,
			btn00Is:false,
			btn01:true,
			btn01Is:false,
			btn02:true,
			btn02Is:false,
			btn03:true,
			btn03Is:false,
			btn04:true,
			btn04Is:false,
			btn05:true,
			btn05Is:false,
			btn06:true,
			btn06Is:false,
			btn07:true,
			btn07Is:false,
			btn08:true,
			btn08Is:false,
			btn09:true,
			btn09Is:false,
			btn010:true,
			btn010Is:false,
			btn011:true,
			btn011Is:false,
			btn012:true,
			btn012Is:false,
			btn013:true,
			btn013Is:false,
			jsbtn:false,
			stopC01:false,
			up_num:false,
			human:require('@/assets/human.png'),
			isHover:false,
			popImg01:'',
			popImg02:'',
			popImg03:'',
			popImgData00:[
				require('@/assets/shinkan.png'),
				require('@/assets/sinkan02.png'),
				require('@/assets/sinkan03.png'),
			],
			popImgData01:[
				require('@/assets/bbq01.png'),
				require('@/assets/bbq00.png'),
				require('@/assets/bbq02.png'),
			],
			popImgData02:[
				require('@/assets/yokohama00.png'),
				require('@/assets/yokohama01.png'),
				require('@/assets/yokohama02.png'),
			],
			popImgData03:[
				require('@/assets/disny00.png'),
				require('@/assets/disny01.png'),
				require('@/assets/disny01.png'),
			],
			popImgData04:[
				require('@/assets/sinkangassyuku00.png'),
				require('@/assets/sinkangassyuku01.png'),
				require('@/assets/sinkangassyuku02.png'),
			],
			popImgData05:[
				require('@/assets/umi.png'),
				require('@/assets/umi01.png'),
				require('@/assets/umi00.png'),
			],
			popImgData06:[
				require('@/assets/kanbu.png'),
				require('@/assets/kanbu00.png'),
				require('@/assets/kanbu02.png'),
			],
			popImgData07:[
				require('@/assets/natugassyuku00.png'),
				require('@/assets/natugassyuku01.png'),
				require('@/assets/natugassyuku02.png'),
			],
			popImgData08:[
				require('@/assets/tokorozawa00.png'),
				require('@/assets/tokorozawa01.png'),
				require('@/assets/tokorozawa02.png'),
			],
			popImgData09:[
				require('@/assets/wasedasai00.png'),
				require('@/assets/wasedasai01.png'),
				require('@/assets/wasedasai02.png'),
			],
			popImgData010:[
				require('@/assets/kuripa00.png'),
				require('@/assets/kuripa01.png'),
				require('@/assets/kuripa02.png'),
			],
			popImgData011:[
				require('@/assets/ramen00.png'),
				require('@/assets/ramen01.png'),
				require('@/assets/harugassyuku00.png'),
			],
			popImgData012:[
				require('@/assets/harugassyuku00.png'),
				require('@/assets/harugassyuku01.png'),
				require('@/assets/harugassyuku00.png'),
			],
			popImgData013:[
				require('@/assets/oikon00.png'),
				require('@/assets/oikon01.png'),
				require('@/assets/oikon02.png'),
			],
			Img00:require('@/assets/shinkan.png'),
			Img01: require('@/assets/bbq00.png'),
			Img02: require('@/assets/yokohama00.png'),
			Img03: require('@/assets/disny00.png'),
			Img04: require('@/assets/sinkangassyuku00.png'),
			Img05: require('@/assets/umi.png'),
			Img06: require('@/assets/kanbu.png'),
			Img07: require('@/assets/natugassyuku00.png'),
			Img08: require('@/assets/tokorozawa00.png'),
			Img09: require('@/assets/wasedasai00.png'),
			Img010: require('@/assets/kuripa00.png'),
			Img011: require('@/assets/ramen00.png'),
			Img012: require('@/assets/harugassyuku00.png'),
			Img013: require('@/assets/oikon00.png'),
			ttlCont:'',
			ttlContData:[
				'新歓活動','BBQ','横浜','ディズニ','新歓合宿','海イベント','幹部最終活動','夏合宿','所沢祭','早稲田祭','クリパ','ラーメン屋飲み会','春合宿','追いコン'
			],
			cont:'',
			contData:[
				'通常の活動を体験します。まあ、ラーメン食べてファミレスに行くだけです！',
				'BBQします！そのあとは近くの海でビーチバレーや日光浴？？笑',
				'新横浜駅の近くのラーメン博物館に行き、そのあとみなとみらいで班別行動で散策します！',
				'ラーメン部でディズニー行きます。全日組とアフ６組に分かれて楽します！',
				'１泊二日で合宿を行います！体育館でレクをして、夜は飲み会！（もちろん、コールなし）、次の日は河口湖でボートに乗り、お昼はほうとうを食べます',
				'勝浦坦々麺を食べ海に行き、海水浴ですで。',
				'3人の幹部のおすすめのラーメン屋に分かれていきます！',
				'早稲田大学ラーメン部前期の最大のイベントです。２泊三日で草津温泉に泊まりあます。3年生と2年生の代替えの最後の夜は号泣です笑',
				'所沢祭にてラーメンの出店を行います。ラーメンの元から一から作ります！',
				'早稲田大学ラーメン部の最大のイベントです。二日間でディズニーより多い集客力を持つ早稲田祭での出店です！有名ラーメン屋さんとのコラボ商品を出します',
				'部員同士がプレゼントを持ち合ってプレゼントを渡し合いをします！',
				'ラーメン屋を貸し切って飲み会を行います！去年はあの有名店を貸し切りに笑',
				'二泊三日でスノボーをやります！初めてでもみんな１日で滑れるようになります！最終日にはイチゴ狩りに行って春も感じます！',
				'大学を卒業なさる4年生のお別れ会です！パーティ会場でご飯を食べてレクレーションをしてお別れの動画を見ます！'

			],
			dayCont:'',
			dayContData:[
				'私たちラーメン部の新歓活動はこの時期の間、平日に週３日（奇数週は月水金、偶数週は火木）の活動となっています。',
				'毎年新入生が入学する5月に行っています暖かい日が続くGWに行います！',
				'毎年５月の後半に行っています！',
				'毎年６月の晴れた日に行っています！',
				'毎年８月の前半に行っています！テスト明けです！',
				'毎年８月の後半に行っています！',
				'毎年９月の前半に行っています！',
				'毎年１０月の前半に行っています！',
				'毎年１１月の前半に行っています！',
				'毎年１２月のクリスマス近辺に行っています！',
				'毎年２月のテスト終わりに行っています！',
				'毎年３月の前半に行っています！',
				'毎年３月の後半に行っています！',
				'a',
			],
			areaCont:'',
			areaContData:[
				'この新歓期間は活動場所は全て高田馬場駅集合となっており、都内はもちろん、首都圏各地から活動に参加しやすい場所で集まります。',
				'千葉県の稲毛海岸で行っています。都内からは少し遠いですが海が近く、食後の運動も最高に楽しいです！',
				'文字通り横浜でやります！',
				'ランドかシーか？それはその時の幹事長の気分次第です笑',
				'山梨県の河口湖に行きます。きれいなペンションに泊まります！',
				'千葉県の御宿に行きます。都内からは遠いですが海がきれいです！',
				'場所は直前まで非公開で、前日に先輩がたが一斉に発表します',
				'草津のホテルです！草津温泉も徒歩圏内の好立地。',
				'早稲田大学の所沢キャンパスで行います！',
				'早稲田大学の早稲田キャンパスです行います！',
				'都内のパーティー会場です！',
				'ラーメン屋某所です！',
				'群馬県のペンションに行きます！',
				'都内の某所です',
			],
			moneyCont:'',
			moneyContData:[
				'予算の面ではこの期間は初めての活動参加者限定でラーメン代を先輩が奢るため活動費は高田馬場までの交通費！となっています。',
				'現地までの交通費と参加費2000円です。食事代は先輩方のおごりですので1円も必要ありません！',
				'現地までの交通費と博物館の入場料500円とラーメン代1000円です。あとは先輩方にお世話になりましょう☺️',
				'ディズニーの代金です。年パス持ってる人はいくしかない！！',
				'交通費、宿泊費、食費全て込みで1万５千円です！',
				'現地までの交通費2000円とラーメン代1000円です１',
				'いつもと同じ交通費とラーメン代です！',
				'交通費、宿泊費、食費全て込みで2万５千円です！',
				'特に参加費は必要ありません！売り上げ次第で打ち上げの楽しさが！笑',
				'特に参加費は必要ありません！売り上げ次第で打ち上げの楽しさが！笑',
				'参加費は2000円です！プレンゼント代は別途各自！',
				'費用は3000円ですが、ラーメン屋がいつもと違うメニューを作成してくれてすごく貴重な体験を味わえます。',
				'交通費、宿泊費、食費全て込みで2万５千円です！',
				'参加費は5000円です！',
			],
			exCont01:'',
			exCont01Data:[
				'先輩方がラーメン代を奢ってくれます。普段いくおすすめのラーメン屋も教えてもらえます！',
				'お肉食べ放題で最高に楽しいです。あ、もちろん野菜も食べてますよ笑',
				'ラーメン博物館では先輩の顔芸？で笑い、みなとみらいでは横浜の遊覧船に乗って遊びました！',
				'上京して初めてディズニーに行きましたが、楽しすぎました！',
				'先輩方が一斉に集まり自己紹介してくれました。あんな先輩いたんだみたいな笑',
				'夏と言ったら！ってイベントです。勝浦坦々麺からすぎますw',
				'すっごく気に入ってもらった先輩との最後の活動です。個人的にプレゼントを渡しました。笑',
				'2年生から3年生の方へのお別れのプレゼンが感動ものでした。自分たちも来年が楽しみになりました１',
				'初めて大学の文化祭でしたが、楽しいです',
				'うわせには聞いていましたが人が多すぎてすごいです。想像以上にラーメンが売れて大変だったけど楽しかったです',
				'みんな色々考え尽くされたプレゼントを渡し合って楽しかったで',
				'有名ラーメン屋さんを本当に貸し切って飲み会を行います笑',
				'人生初めてのスノボーでしたが１日で滑れるようになり二日目には山頂から滑れるようになりました！',
				'あったことのない先輩もいましたがもらい泣きしました。',
			],
			exCont02:'',
			exCont02Data:[
				'先輩方が優しく出迎えてくれます。また、いずれ同期となるメンバーとの距離が近づきやすいため、学内、学外の交友関係が広がりおすすめのイベントです！',
				'先輩方の盛り上げが上手です笑ラーメンはあんまり食べないけど、BBQの後に先輩方に千葉の名店に連れてってもらえました！',
				'自作のカップラーメンを作りました。オリジナルのラーメンを作るという貴重な体験ができました！',
				'高校生からディズニーガチ勢だったけど大人数で行ったのは初めてでした。ラーメン部楽しい！！',
				'同期の絆がめちゃ深まります！このサークルに軸を決めたのもこのイベントでした笑',
				'水着ないなって人でも大丈夫です。正直、普段着でビーチで遊んでる人が半数です笑',
				'最後だったので思わず泣いてしまいました。半年間だけだったのけど密度の濃い日々を過ごせたのだなって感動しました。',
				'一年生同士の決起会も行いました。この時に同期で作るtシャツのデザインを決めました！',
				'2年生の方ととても近い距離で行うので2年生の方と仲良くなれます！',
				'高校の同級生を招待してラーメンを食べてもらいました。美味しかったみたいです笑',
				'クリスマスにラーメン屋限定のスプーンをもらいました。さすがラーメン部笑',
				'有名ラーメン屋の店長が独自に作る料理はお酒とすごく合いました！',
				'イチゴ狩りを久しぶりにしましたが楽しかったです！',
				'自分たちも4年後にはこんな風に追い出されると嬉しいなって感動しました'
			]
		}
	},
	methods:{
		change(num){
			if(num == 2)
			{
				this.out = 1
				this.selected05 = true
			}
			else if(num == 1)
			{
				this.out = 2
				this.selected05 = true
			}
		},
		up(num)
		{
			if(num == 0){
				this.ttlCont = this.ttlContData[num]
				this.cont = this.contData[num]
				this.dayCont = this.dayContData[num]
				this.areaCont = this.areaContData[num]
				this.moneyCont = this.moneyContData[num]
				this.exCont01 = this.exCont01Data[num]
				this.exCont02 = this.exCont02Data[num]
				this.popImg01 = this.popImgData00[0]
				this.popImg02 = this.popImgData00[1]
				this.popImg03 = this.popImgData00[2]
				this.up_num = true
			}
			else if(num == 1)
			{
				this.ttlCont = this.ttlContData[num]
				this.cont = this.contData[num]
				this.dayCont = this.dayContData[num]
				this.areaCont = this.areaContData[num]
				this.moneyCont = this.moneyContData[num]
				this.exCont01 = this.exCont01Data[num]
				this.exCont02 = this.exCont02Data[num]
				this.popImg01 = this.popImgData01[0]
				this.popImg02 = this.popImgData01[1]
				this.popImg03 = this.popImgData01[2]
				this.up_num = true
			}
			else if(num == 2)
			{
				this.ttlCont = this.ttlContData[num]
				this.cont = this.contData[num]
				this.dayCont = this.dayContData[num]
				this.areaCont = this.areaContData[num]
				this.moneyCont = this.moneyContData[num]
				this.exCont01 = this.exCont01Data[num]
				this.exCont02 = this.exCont02Data[num]
				this.popImg01 = this.popImgData02[0]
				this.popImg02 = this.popImgData02[1]
				this.popImg03 = this.popImgData02[2]
				this.up_num = true
			}
			else if(num == 3)
			{
				this.ttlCont = this.ttlContData[num]
				this.cont = this.contData[num]
				this.dayCont = this.dayContData[num]
				this.areaCont = this.areaContData[num]
				this.moneyCont = this.moneyContData[num]
				this.exCont01 = this.exCont01Data[num]
				this.exCont02 = this.exCont02Data[num]
				this.popImg01 = this.popImgData03[0]
				this.popImg02 = this.popImgData03[1]
				this.popImg03 = this.popImgData03[2]
				this.up_num = true
			}
			else if(num == 4)
			{
				this.ttlCont = this.ttlContData[num]
				this.cont = this.contData[num]
				this.dayCont = this.dayContData[num]
				this.areaCont = this.areaContData[num]
				this.moneyCont = this.moneyContData[num]
				this.exCont01 = this.exCont01Data[num]
				this.exCont02 = this.exCont02Data[num]
				this.popImg01 = this.popImgData04[0]
				this.popImg02 = this.popImgData04[1]
				this.popImg03 = this.popImgData04[2]
				this.up_num = true
			}
			else if(num == 5)
			{
				this.ttlCont = this.ttlContData[num]
				this.cont = this.contData[num]
				this.dayCont = this.dayContData[num]
				this.areaCont = this.areaContData[num]
				this.moneyCont = this.moneyContData[num]
				this.exCont01 = this.exCont01Data[num]
				this.exCont02 = this.exCont02Data[num]
				this.popImg01 = this.popImgData05[0]
				this.popImg02 = this.popImgData05[1]
				this.popImg03 = this.popImgData05[2]
				this.up_num = true
			}
			else if(num == 6)
			{
				this.ttlCont = this.ttlContData[num]
				this.cont = this.contData[num]
				this.dayCont = this.dayContData[num]
				this.areaCont = this.areaContData[num]
				this.moneyCont = this.moneyContData[num]
				this.exCont01 = this.exCont01Data[num]
				this.exCont02 = this.exCont02Data[num]
				this.popImg01 = this.popImgData06[0]
				this.popImg02 = this.popImgData06[1]
				this.popImg03 = this.popImgData06[2]
				this.up_num = true
			}
			else if(num == 7)
			{
				this.ttlCont = this.ttlContData[num]
				this.cont = this.contData[num]
				this.dayCont = this.dayContData[num]
				this.areaCont = this.areaContData[num]
				this.moneyCont = this.moneyContData[num]
				this.exCont01 = this.exCont01Data[num]
				this.exCont02 = this.exCont02Data[num]
				this.popImg01 = this.popImgData07[0]
				this.popImg02 = this.popImgData07[1]
				this.popImg03 = this.popImgData07[2]
				this.up_num = true
			}
			else if(num == 8)
			{
				this.ttlCont = this.ttlContData[num]
				this.cont = this.contData[num]
				this.dayCont = this.dayContData[num]
				this.areaCont = this.areaContData[num]
				this.moneyCont = this.moneyContData[num]
				this.exCont01 = this.exCont01Data[num]
				this.exCont02 = this.exCont02Data[num]
				this.popImg01 = this.popImgData08[0]
				this.popImg02 = this.popImgData08[1]
				this.popImg03 = this.popImgData08[2]
				this.up_num = true
			}
			else if(num == 9)
			{
				this.ttlCont = this.ttlContData[num]
				this.cont = this.contData[num]
				this.dayCont = this.dayContData[num]
				this.areaCont = this.areaContData[num]
				this.moneyCont = this.moneyContData[num]
				this.exCont01 = this.exCont01Data[num]
				this.exCont02 = this.exCont02Data[num]
				this.popImg01 = this.popImgData09[0]
				this.popImg02 = this.popImgData09[1]
				this.popImg03 = this.popImgData09[2]
				this.up_num = true
			}
			else if(num == 10)
			{
				this.ttlCont = this.ttlContData[num]
				this.cont = this.contData[num]
				this.dayCont = this.dayContData[num]
				this.areaCont = this.areaContData[num]
				this.moneyCont = this.moneyContData[num]
				this.exCont01 = this.exCont01Data[num]
				this.exCont02 = this.exCont02Data[num]
				this.popImg01 = this.popImgData010[0]
				this.popImg02 = this.popImgData0104[1]
				this.popImg03 = this.popImgData010[2]
				this.up_num = true
			}
			else if(num == 11)
			{
				this.ttlCont = this.ttlContData[num]
				this.cont = this.contData[num]
				this.dayCont = this.dayContData[num]
				this.areaCont = this.areaContData[num]
				this.moneyCont = this.moneyContData[num]
				this.exCont01 = this.exCont01Data[num]
				this.exCont02 = this.exCont02Data[num]
				this.popImg01 = this.popImgData011[0]
				this.popImg02 = this.popImgData011[1]
				this.popImg03 = this.popImgData011[2]
				this.up_num = true
			}
			else if(num == 12)
			{
				this.ttlCont = this.ttlContData[num]
				this.cont = this.contData[num]
				this.dayCont = this.dayContData[num]
				this.areaCont = this.areaContData[num]
				this.moneyCont = this.moneyContData[num]
				this.exCont01 = this.exCont01Data[num]
				this.exCont02 = this.exCont02Data[num]
				this.popImg01 = this.popImgData012[0]
				this.popImg02 = this.popImgData012[1]
				this.popImg03 = this.popImgData011[2]
				this.up_num = true
			}
			else if(num == 13)
			{
				this.ttlCont = this.ttlContData[num]
				this.cont = this.contData[num]
				this.dayCont = this.dayContData[num]
				this.areaCont = this.areaContData[num]
				this.moneyCont = this.moneyContData[num]
				this.exCont01 = this.exCont01Data[num]
				this.exCont02 = this.exCont02Data[num]
				this.popImg01 = this.popImgData013[0]
				this.popImg02 = this.popImgData013[1]
				this.popImg03 = this.popImgData013[2]
				this.up_num = true
			}

		},
		acin(){
			this.selected01 = true
			this.selected02 = false
		},
		acout(){
			this.selected01 = false
			this.selected02 = true
		},
		acin01(){
			this.selected03 = false
			this.selected04 = true
		},
		acout01(){
			this.selected03 = true
			this.selected04 = false
		},
		btnOver(num){
			if(num == 0)
			{
				this.btn00 = false
				this.btn00Is = true
			}
			else if(num == 1)
			{
				this.btn01 = false
				this.btn01Is = true
			}
			else if(num == 2)
			{
				this.btn02 = false
				this.btn02Is = true
			}
			else if(num == 3)
			{
				this.btn03 = false
				this.btn03Is = true
			}
			else if(num == 4)
			{
				this.btn04 = false
				this.btn04Is = true
			}
			else if(num == 5)
			{
				this.btn05 = false
				this.btn05Is = true
			}
			else if(num == 6)
			{
				this.btn06 = false
				this.btn06Is = true
			}
			else if(num == 7)
			{
				this.btn07 = false
				this.btn07Is = true
			}
			else if(num == 8)
			{
				this.btn08 = false
				this.btn08Is = true
			}
			else if(num == 9)
			{
				this.btn09 = false
				this.btn09Is = true
			}
			else if(num == 10)
			{
				this.btn010 = false
				this.btn010Is = true
			}
			else if(num == 11)
			{
				this.btn011 = false
				this.btn011Is = true
			}
			else if(num == 12)
			{
				this.btn012 = false
				this.btn012Is = true
			}
			else if(num == 13)
			{
				this.btn013 = false
				this.btn013Is = true
			}
		},
		btnLeave(num){
			if(num == 0)
			{
				this.btn00 = true
				this.btn00Is = false
			}
			else if(num == 1)
			{
				this.btn01 = true
				this.btn01Is = false
			}
			else if(num == 2)
			{
				this.btn02 = true
				this.btn02Is = false
			}
			else if(num == 3)
			{
				this.btn03 = true
				this.btn03Is = false
			}
			else if(num == 4)
			{
				this.btn04 = true
				this.btn04Is = false
			}
			else if(num == 5)
			{
				this.btn05 = true
				this.btn05Is = false
			}
			else if(num == 6)
			{
				this.btn06 = true
				this.btn06Is = false
			}
			else if(num == 7)
			{
				this.btn07 = true
				this.btn07Is = false
			}
			else if(num == 8)
			{
				this.btn08 = true
				this.btn08Is = false
			}
			else if(num == 9)
			{
				this.btn09 = true
				this.btn09Is = false
			}
			else if(num == 10)
			{
				this.btn010 = true
				this.btn010Is = false
			}
			else if(num == 11)
			{
				this.btn011 = true
				this.btn011Is = false
			}
			else if(num == 12)
			{
				this.btn012 = true
				this.btn012Is = false
			}
			else if(num == 13)
			{
				this.btn013 = true
				this.btn013Is = false
			}
		},
		del(){
			this.up_num = false
		}
	}

}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400&family=Potta+One&display=swap');
$maincolor:#9B072D;
$maincolor_50:#9b072c85;
$subcolor:rgb(48, 48, 48);
$subcolor_50:rgba(48, 48, 48, 0.5);

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
.left{
	width: 40%;
	background: $maincolor_50;
}

.jsblue{
	margin: 5% 35%;
	width: 30%;
	border: $maincolor dotted 2px;
	background: $maincolor;
	color: white;
}

.defbtn{
	margin: 5% 35%;
	width: 30%;
	border: $maincolor solid 2px;
	background: white;
	color: $maincolor;
}

.jsbtn{
	margin: 5% 35%;
	width: 30%;
	border: $maincolor solid 2px;
	background: $maincolor;
	color: white;
	cursor: pointer;
}

.blue{
	cursor: pointer;
	color: white;
	background: $maincolor;
	width: 20%;
	margin: 0 40%;
	padding: 1% 0;
}

.defblue{
	color: white;
	border: 2px $maincolor_50 solid;
	width: 20%;
	margin: 0 40%;
	padding: 1% 0;
	cursor: default;
}


p{
	font-family: 'Noto Sans JP', sans-serif;
	padding: 0 2%;
}
h1{
	color: $maincolor;
}

h2{
	color: $maincolor;
}

h3{
	padding: 1%;
}


.js{
	filter: blur(6px);
}
.right{
	width: 40%;
	background: $maincolor_50;
}
h5{
	font-size: 30px;
	margin: 2%;
	color: white;
}
img{
	width: 100%;
	height: 100%;
}
.ig{
	margin:1%;
}
.img{
	padding: 2% 2% 0 2%;
}
.img02{
	width: 100%;
}

.popImg{
	margin: 0 5%;
	padding:  0;
}

.popImg-size{
	width: 10%;
	margin: 5% 45%;
	height: 40%;
}
.bu{
	display: flex;
	justify-content: center;
	width: 60%;
	margin: 0 20%;
	padding: 1%;
}

h2{
	border-bottom: 2px solid $subcolor;
	margin: 0;
}
.m{
	position: absolute;
	margin: 0;
	font-size: 2rem;
	left: 0;
	top: 0;
	color: $maincolor;
}

.m span{
	font-size: 1rem;
	color: $maincolor_50;
}

.top{
	display: flex;
	text-align: center;
	width: 90%;
	margin: 5% 5% 0 5%;
	background: whitesmoke;
}

.btn{
	margin: 5% 35%;
	width: 30%;
	border: $maincolor dotted 2px;
	background: $maincolor;
	color: white;
}

.btn_test{
	width: 80%;
	margin: 10% 10%;
	border: $maincolor dotted 2px;
	color: $maincolor;
}

.el_btn_is{
	background: $maincolor;
	width: 50%;
	font-size: 20px;
	padding: 1% 0;
	color: white;
}

.el_btn_def{
	background:$maincolor_50;
	width: 50%;
	font-size: 20px;
	padding: 1% 0;
	color:$maincolor_50;
}
h4{
}

.cont{
	width: 85%;
	margin-left: 7.5%;
	display: flex;
	flex-wrap:wrap;
	justify-content: space-evenly;
}

.cont_cont01{
	width: 40%;
	padding: 0 5%;
	background: $subcolor_50;
	border-bottom: solid 1px rgba(255, 0, 0, 0.521);
	display: flex;
	justify-content:space-evenly;
	flex-direction: wrap;
	position: relative;
}

.cont_cont02{
	width: 40%;
	padding: 0 5%;
	background: $subcolor_50;
	border-bottom: solid 2px $maincolor_50;
	display: flex;
	justify-content:space-evenly;
	flex-direction: wrap;
	position: relative;
}

.card{
	background: white;
	width: 50%;
	margin:  5%;
}

.card01{
	background: white;
	border: 2px solid black;
	width: 40%;
	margin: 5% 0;
}

.card01{
	background: white;
	border: 2px solid black;
	margin: 5% 0;


}

.up_bl{
	position: absolute;
	z-index: 2;
	left: 5%;
	top: 5%;
	width: 90%;
	background: rgba(0, 0, 0, 0.795);
	border: 2px solid red;
}
.del{
	margin: 1%;
	position: absolute;
	top: 0;
	right: 0;
	color: white;
}
.up_cont{
	display: flex;
	justify-content: space-evenly;
	color: white;
	margin: 1%;
}

.ly{
	position: absolute;
	top: 0;
	left: 10%;
	width: 90%;
}
</style>