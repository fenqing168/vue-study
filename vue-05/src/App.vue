<template>
    <div>
      <img class="logo" src="./assets/logo.png" alt="logo"/>
      <HelloWolrd />
    </div>
</template>

<script>

  import HelloWolrd from './components/HelloWorld'

  export default {
    name: 'App',
    components: {
      HelloWolrd
    }
  }
</script>

<style scoped>

  .logo{
    width: 200px;
    height: 200px;
  }

</style>
