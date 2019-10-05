<template>
  <div v-if="selectNum > 0">
    <input type="checkbox" @click="cutSelect" v-model="isAll" >{{selectNum}}/{{taskNum}}
    <button type="button" @click="del" class="btn btn-danger">删除</button>
  </div>
</template>

<script>
  import 'bootstrap/dist/css/bootstrap.css'

  export default {
    props: ['selectNum', 'taskNum', 'delTask', 'isAll', 'cutSelect'],
    name: 'Del',
    methods:{
      del(){
        if(window.confirm('确定吗？')){
          this.delTask()
        }
      }
    }
  }
</script>

<style scoped>

</style>
