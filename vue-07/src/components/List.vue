<template>
  <div>
    <Item v-for="(task, index) in tasks" :key="index" :index="index" :task="task" :delByIndex="delByIndex"/>
  </div>
</template>

<script>
  import 'bootstrap/dist/css/bootstrap.css'
  import Item from './Item'

  export default {
    props:['tasks', 'delByIndex'],
    name: 'List',
    components: {
      Item
    }
  }
</script>

<style scoped>

</style>
