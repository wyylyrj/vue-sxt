<template>
    <div>
      <button @click="show = !show">Toggle</button>
      <transition
        name="custom-classes-transition"
        enter-active-class="animated rollIn"
        leave-active-class="animated rollOut"
      >
        <p v-if="show" class="box">hello</p>
      </transition>
      <input v-focus type="text"/>
    </div>
</template>

<script>
    export default {
        name: "anim",
      data () {
          return {
            show: true
          }
      }
    }
</script>

<style scoped lang="css">
  .box{
    width: 100px;
    height: 100px;
    background: yellowgreen;
  }
  /*.fade-enter, .fade-leave-to{*/
    /*opacity: 0;*/
    /*width: 0px;*/
    /*height: 0px;*/
  /*}*/
  /*.fade-enter-to, .fade-leave{*/
    /*opacity: 1;*/
    /*width: 100px;*/
    /*height: 100px;*/
  /*}*/
  /*.fade-enter-active, .fade-leave-active{*/
    /*transition: all 1s;*/
  /*}*/
</style>
