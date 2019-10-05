<template>
  <div id="app">
    <div class="container">
      <Header :addTask="addTask"/>
      <List :tasks="tasks" :delByIndex="delByIndex"/>
      <Del :selectNum="selectNum" :taskNum="taskNum" :delTask="delTask" :isAll="isAll" :cutSelect="cutSelect"/>
    </div>
  </div>
</template>

<script>
  import 'bootstrap/dist/css/bootstrap.css'
  import Header from './components/Header'
  import List from './components/List'
  import Del from './components/Del'

  export default {
    name: 'App',
    components: {
      Header,
      List,
      Del
    },
    data () {
      return {
        tasks: [
          {
            name: 'xxx',
            status: false
          },
          {
            name: 'yyy',
            status: false
          }
        ],
      }
    },
    computed:{
      selectNum(){
        let count = 0
        this.tasks.forEach(i => {
          i.status && count++
        })
        return count
      },
      taskNum(){
        return this.tasks.length
      },
      isAll(){
        let isall = true
        this.tasks.forEach(i => {
          isall = isall && i.status
        })
        return isall
      }
    },
    methods: {
      addTask (task) {
        this.tasks.unshift(task)
      },
      delTask(){
        this.tasks = this.tasks.filter(i => !i.status)
      },
      delByIndex(index){
        console.log(this.tasks)
        this.tasks.splice(index, 1)
      },
      cutSelect(){
        let all = this.isAll
        const { tasks } = this
        tasks.forEach(i => i.status = !all)
      }
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
