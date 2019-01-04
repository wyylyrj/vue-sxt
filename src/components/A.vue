<template>
    <div>
      组件A：{{ item }}
      <button @click="changeValue">改变</button>
    </div>
</template>

<script>
    export default {
        name: "A",
      data () {
          return {
            item: '默认'
          }
      },
      methods: {
        changeValue () {
          this.item = '改变';
        }
      }
    }
</script>

<style scoped>

</style>
