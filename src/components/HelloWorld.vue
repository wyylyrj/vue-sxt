<template>
  <div class="hello">
    {{"哈哈"}}
    {{20+1}}
    {{"ok" ? 'yes' : 'no'}}
    {{"hello".split('').reverse().join('')}}
    {{msg}}
    <p v-once>{{msg}}</p>
    {{hello}}
    <div v-html="hello"></div>
    <a v-bind:href="url">{{url_name}}</a>
    <div :class="divClass">容器</div>
    <div :class="divClass+'-1'">容器1</div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      hello: '<h3>Hello H3</h3>',
      url: 'http://taobao.com',
      url_name: '淘宝',
      divClass: 'isActive'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
