<template>
  <div id="app">
    <Header 
      v-on:change01="changeTop()"
      v-on:change02="changeAbout()"
      v-on:change03="changeHistry()"
      v-on:change04="changeHead()"
      v-on:change05="changeContact()" >
    </Header>
    <Top v-if="tab == 1"></Top>
    <About v-if="tab == 2"></About>
    <Histry v-if="tab == 3"></Histry>
    <Head v-if="tab == 4"></Head>
    <Contact v-if="tab == 5"></Contact>
    {{tab}}
  </div>
</template>

<script>
import 'normalize.css'
import Header from './components/Header.vue'
import Top from './components/Top.vue'
import About from './components/About.vue'
import Histry from './components/Histry.vue'
import Head from './components/Head.vue'
import Contact from './components/Contact.vue'

export default {
  name: 'App',
  components:{
    Header,
    Top,
    About,
    Histry,
    Head,
    Contact

  },
  data(){
    return{
      isPop:false,
      tab:1
    }
  },
  methods:{
    changeTop(){
      this.tab = 1
    },
    changeAbout(){
      this.tab = 2
    },
    changeHistry(){
      this.tab = 3
    },
    changeHead(){
      this.tab = 4
    },
    changeContact(){
      this.tab = 5
    }
  }
}
</script>

<style lang="scss" scoped>
$maincolor:#9B072D;
$subcolor:#777777;

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
