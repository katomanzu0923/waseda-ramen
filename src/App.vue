<template>
  <div id="app">
    <Header 
      v-on:change00="changeTop()"
      v-on:change01="changeAbout()"
      v-on:change02="changeHistry()"
      v-on:change03="changeHead()"
      v-on:change04="changePast()"
      v-on:change05="changeFirm()" 
      v-on:change06="changeContact()" >
    </Header>
    <Top v-if="tab == 0" class="top"></Top>
    <About v-if="tab == 1"></About>
    <Histry v-if="tab == 2"></Histry>
    <Head v-if="tab == 3"></Head>
    <Past v-if="tab == 4"></Past>
    <Firm v-if="tab == 5"></Firm>
    <Contact v-if="tab == 6"></Contact>
    {{num}}

  </div>
</template>

<script>
import 'normalize.css'
import Header from './components/Header.vue'
import Top from './components/Top.vue'
import About from './components/About.vue'
import Histry from './components/Histry.vue'
import Head from './components/Head.vue'
import Past from './components/Past.vue'
import Firm from './components/Firm.vue'
import Contact from './components/Contact.vue'

export default {
  name: 'App',
  components:{
    Header,
    Top,
    About,
    Histry,
    Head,
    Past,
    Firm,
    Contact,
  },
  data(){
    return{
      isPop:false,
      tab:0,
      num:''
    }
  },
  methods:{
    changeTop(){
      this.tab = 0
    },
    changeAbout(){
      this.tab = 1
    },
    changeHistry(){
      this.tab = 2
    },
    changeHead(){
      this.tab = 3
    },
    changePast(){
      this.tab = 4
    },
    changeFirm(){
      this.tab = 5
    },
    changeContact(){
      this.tab = 6
    }
  }
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Potta+One&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Potta+One&display=swap');

$maincolor:#9B072D;
$subcolor:#777777;

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 100vw;
  font-family: 'Potta One', cursive;
  
}
.event{
}
.top{
  position: absolute;
  top: 0;
  z-index: -2;
}
</style>
