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
    <div v-if="flag">孙悟空</div>
    <div v-else>通臂猿猴</div>
    <div v-show="flag">真三国无双</div>
    <ul>
      <li v-for="name in names">
        {{name}}
      </li>
    </ul>
    <ul>
      <li v-for="(person,index) in persons" :key="index">
        {{index}}-{{person.name}}-{{person.age}}
      </li>
    </ul>
    <ul>
      <li v-for="(item,key,index) in obj" :key="index">
        {{index}}-{{key}}-{{item}}
      </li>
    </ul>
    <ul>
      <li v-for="(item,index) in helloArr" :key="index">
        {{item}}
      </li>
    </ul>
    <button @click="clickHandler('哈哈')">按钮</button>
    <button @click="addHelloArr">添加</button>
  </div>
</template>

<script>

  import qs from 'qs';

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      hello: '<h3>Hello H3</h3>',
      url: 'http://taobao.com',
      url_name: '淘宝',
      divClass: 'isActive',
      flag: false,
      names: ['iwen','iwe','ice'],
      helloArr: ['hello1','hello2','hello3'],
      persons: [
        {
          name: 'iwen',
          age: 20
        },
        {
          name: 'iwe',
          age: 200
        },
        {
          name: 'ice',
          age: 2000
        }
      ],
      obj: {
        name: 'iwen',
        age: 20
      }
    }
  },
  methods: {
    clickHandler (data) {
      console.log(data);
      console.log(event);
      this.flag = !this.flag;
    },
    addHelloArr () {
      this.helloArr.push('hello4');
    }
  },
  mounted() {
    this.$axios.get('http://www.wwtliu.com/sxtstu/news/juhenews.php',{
      params: {
        type: 'yule',
        count: 30
      }
    })
      .then(res => {
        console.log(res.data);
      })
      .catch(error => {
        console.log(error);
      })
    this.$axios.post('http://www.wwtliu.com/sxtstu/blueberrypai/login.php',qs.stringify({

        user_id: 'iwen@qq.com',
        password: 'iwen123',
        verification_code: 'crfvw'

    }))
      .then(res => {
        console.log(res.data)
      })
      .catch(error => {
        console.log(error)
      })
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
