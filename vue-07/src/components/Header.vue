<template>
  <div class="form-group">
    <input type="text" class="form-control" v-model="taskName" @keyup.enter="add" placeholder="请输入任务名称，按回车确认">
  </div>
</template>

<script>
  import 'bootstrap/dist/css/bootstrap.css'

  export default {
    props: {
      'addTask': {
        type: Function,
        required: true
      }
    },
    name: 'Header',
    data(){
      return {
        taskName: null,
      }
    },
    methods:{
      add(){
        if(!this.taskName){
          alert('请输入任务名称')
          return;
        }
        if(window.confirm(`确定添加${this.taskName}吗？`)){
          this.addTask({
            name: this.taskName,
            status: false
          })
          this.taskName = ''
        }
      }
    }
  }
</script>

<style scoped>

</style>
