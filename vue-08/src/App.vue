<template>
  <div >
    <input type="text" v-model="q" placeholder="关键字" />
    <div v-if="!hotProject.url">加载中~~~</div>
    <div v-else>
      最好的项目为：<a target="_blank" :href="hotProject.url">{{hotProject.name}}</a>
    </div>
  </div>

</template>

<script>
import './api-path/third'
import axios from 'axios'

export default {
  name: 'App',
  data () {
    return {
      q: null,
      hotProject: {
        name: null,
        url: null
      }
    }
  },
  computed: {
  },
  mounted () {
    this.getAxiosData()
  },
  watch:{
    q:{
      deep:true,
      handler(){
        this.getAxiosData()
      }
    }
  },
  methods: {
    getData(){
      this.$http.get(window.GIT_HUB_HOT, {
        params: {
          q: this.q,
          sort: 'stars'
        }
      }).then((res) => {
        if(res.data.items.length != 0){
          const { name, html_url } = res.data.items[0]
          this.hotProject = {
            name: name,
            url: html_url
          }
        }
      })
    },
    getAxiosData(){
      axios.get(window.GIT_HUB_HOT, {
        params: {
          q: this.q,
          sort: 'stars'
        }
      }).then((res) => {
        if(res.data.items.length != 0){
          const { name, html_url } = res.data.items[0]
          this.hotProject = {
            name: name,
            url: html_url
          }
        }
      })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
