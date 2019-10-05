<template>
  <div>
    <header class="main-header">
      <h3>
        Vue 评论系统
      </h3>
    </header>
    <div class="box container">
      <Add :addComment="addComment"/>
      <List :comments="comments" :delComment="delComment"/>
    </div>
  </div>
</template>

<script>
  import List from './components/List'
  import Add from './components/Add'

  export default {
    name: 'App',
    components: {
      List,
      Add
    },
    data () {
      return {
        comments:[
          {
            name: 'fenqing',
            content: 'vue 可以'
          },
          {
            name: '王顶',
            content: 'vue 简单'
          }
        ]
      }
    },
    methods: {
      addComment(comment){
        console.log(comment)
        this.comments.unshift(comment)
      },
      delComment(index){
        this.comments.splice(index, 1)
      }
    }
  }
</script>

<style>
  .main-header{
    text-align: center;
  }
  .box > *{
    float: left;
  }
</style>
