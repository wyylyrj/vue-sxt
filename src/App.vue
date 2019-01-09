<template>
  <div id="app">
    <img src="./assets/logo.png">
    <Parent/>
    <button @click="changeComponent">切换组件</button>
    <keep-alive>
      <component v-bind:is="currentComponent"></component>
    </keep-alive>
    <anim></anim>
    <HelloWorld></HelloWorld>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import VueDemo from './components/VueDemo'
import Parent from './components/Parent'
import A from './components/A'
import B from './components/B'
import Anim from './components/Anim'

export default {
  name: 'App',
  components: {
    HelloWorld,
    VueDemo,
    Parent,
    A,
    B,
    Anim
  },
  data () {
    return {
      flag: true,
      currentComponent: A
    }
  },
  methods: {
    changeComponent () {
      if(this.flag){
        this.flag = false;
        this.currentComponent = B;
      }else{
        this.flag = true;
        this.currentComponent = A;
      }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
