<template>
  <div class="child">
    子组件
    {{title}}--{{age}}
    <button @click="sendMoney">赚了</button>
    <div>称号：{{nick}}</div>
    <div>父亲：{{parent}}</div>
    <ul>
      <li v-for="g in girlFriends">{{g}}</li>
    </ul>
  </div>
</template>

<script>
    export default {
      name: "child",
      data () {
        return {

        }
      },
      // props: ['title','age'],
      props: {
        title: String,
        age: Number,
        nick: {
          type: String,
          default: '国民老公'
        },
        parent: {
          type: String,
          required: true
        },
        girlFriends: {
          type: Array,
          default: function () {
            return ['aaa','bbb']
          }
        }
      },
      methods: {
        sendMoney () {
          this.$emit('money','赚了5个亿！')
        }
      }
    }
</script>

<style scoped>

</style>
