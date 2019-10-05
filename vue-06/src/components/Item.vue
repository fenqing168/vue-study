<template>
  <div class="item">
    <div class="item-title">
      <div>{{comment.name}}说：</div>
      <div>
        <a class="btn btn-info" @click.prevent="delItem" role="button">删除</a>
      </div>
    </div>
    <div class="item-content">
      <p>{{comment.content}}</p>
    </div>
  </div>
</template>

<script>
  import 'bootstrap/dist/css/bootstrap.css'

  export default {
    props:{
      'comment': Object,
      'index': Number,
      'delComment': {
        type: Function,
        required: true
      }
    },
    name: 'Item',
    methods: {
      delItem(){
        if(window.confirm(`确定删除${this.comment.name}的评论吗？`)){
          this.delComment(this.index)
        }
      }
    },
  }
</script>

<style scoped>
  .item{
    border: 1px black solid;
    border-radius: 5px;
  }
  .item .item-title{
    display: flex;
  }
  .item-title > div{
    line-height: 40px;
    font-size: 16px;
    font-weight: 400;
  }
  .item > .item-content{
    font-size: 12px;
    color: #666;
  }
</style>
