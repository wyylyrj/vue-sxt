<template>
  <div class="parent">
    父组件 {{ money }}
    <child @money="getMoney" :age="age" title="一个小目标：一个亿" parent="王健林"></child>
  </div>
</template>

<script>
  import Child from './Child'
    export default {
      name: "parent",
      components: {
        Child
      },
      data () {
          return {
            money: '',
            age:30
          }
      },
      methods: {
        getMoney (data) {
          this.money = data
        }
      }
    }
</script>

<style scoped>

</style>
