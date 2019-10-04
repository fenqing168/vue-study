<template>
  <div>
    <p class="msg">{{msg}}</p>
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data () {
      return {
        msg: 'Hello World Component'
      }
    }
  }
</script>

<style scoped>
  .msg {
    color: red;
    font-size: 30px;
  }
</style>
