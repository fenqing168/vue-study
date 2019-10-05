<template>
  <div>
    <form class="add-form">
      <div class="form-group">
        <label for="username">用户名</label>
        <input v-model="comment.name" type="email" class="form-control" id="username" placeholder="用户名">
      </div>
      <div class="form-group">
        <label for="content">评论内容</label>
        <textarea v-model="comment.content" type="email" class="form-control" id="content" placeholder="评论内容"></textarea>
      </div>
      <div class="form-group">
        <button @click="add" type="button" class="btn btn-primary">提交</button>
      </div>
    </form>
  </div>
</template>

<script>
  import 'bootstrap/dist/css/bootstrap.css'
  export default {
    props: {
      addComment: {
        type: Function,
        required: true
      }
    },
    name: 'Add',
    data (){
      return{
        comment:{}
      }
    },
    methods: {
      add(){
        const {name, content} = this.comment;
        if(!name || !content){
          alert('数据不对！')
          return
        }
        console.log(this.comment)
        this.addComment(this.comment)
        this.comment = {}
      }
    }
  }
</script>

<style scoped>
  .add-form{
    width: 400px;
  }
  .add-form textarea[class='form-control']{
    height: 200px;
  }
</style>
