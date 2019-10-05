<template>
  <div class="list">
    <h3>回复评论:</h3>
    <div>
      <h3 v-show="comments.length === 0">无</h3>
      <Item v-for="(comment, index) in comments" :comment="comment" :index="index" :key="index" :delComment="delComment"/>
    </div>
  </div>
</template>

<script>
  import Item from './Item'
  export default {
    props: ['comments', 'delComment'],
    name: 'List',
    components: {
      Item
    }
  }
</script>

<style scoped>
.list{
  width: 400px;
}
</style>
