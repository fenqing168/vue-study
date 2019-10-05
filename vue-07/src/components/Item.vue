<template>
  <div class="item" @mouseenter="isSelect = true" @mouseleave="isSelect = false">
    <label style="width: 100%">
      <input type="checkbox" v-model="task.status">{{task.name}}
      <button v-if="isSelect" type="button" @click="delIndex" class="btn btn-danger">删除</button>
    </label>
  </div>
</template>

<script>

  import 'bootstrap/dist/css/bootstrap.css'
  export default {
    props: ['task', 'index', 'delByIndex'],
    name: 'Item',
    data(){
      return{
        isSelect:false
      }
    },
    methods:{
      delIndex(){
        this.delByIndex(this.index)
      }
    }
  }
</script>

<style scoped>
.item{
  border: 1px #333 solid;
  box-shadow: 2px 2px 3px #999;
}
.item:hover{
  background: beige;
}
</style>
