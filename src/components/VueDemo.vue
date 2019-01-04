<template>
  <div>
    {{getMsg}}
    <div class="old" :class="{active:flag,'txt':flag}">
      {{getMsg}}
      {{mMsg()}}
    </div>
  </div>
    
</template>

<script>
    export default {
      name: "VueDemo",
      data () {
        return {
          msg: 'hello',
          flag: true,
          active: 'active'
        }
      },
      computed: {
        getMsg() {
          return this.msg.split('').reverse().join('')
        }
      },
      methods: {
        mMsg() {
          return this.msg.split('').reverse().join('')
        }
      }
    }
</script>

<style scoped>
  .active{
    color: red;
  }

  .txt{
    font-size: 30px;
  }

</style>
