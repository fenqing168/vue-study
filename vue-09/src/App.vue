<template>
  <div>
    <input type="text" class="form-control" @keyup="getKeywords" placeholder="关键字" v-model="keyword">
    <button @click="getKeywords">搜索</button>
    <ul v-if="keywords.length != 0">
      <li v-for="(keyword, index) in keywords" :key="index">{{keyword}}</li>
    </ul>
  </div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import axios from 'axios'

export default {
  name: 'App',
  data () {
    return {
      keyword: null,
      keywords: []
    }
  },
  mounted () {
    // this.getKeywords()
  },
  methods: {
    getKeywords () {
      if (!this.keyword || this.keyword === '') {
        this.keywords = []
        console.log(this)
        return
      }
      const arr = []
      for (let i = 0; i < 10; i++) {
        arr.push(
          this.keyword + String.fromCharCode(
            parseInt(
              Math.random() * 100 + ''
            )
          )
        )
      }
      this.keywords = arr
    }
  }
}
</script>

<style>
</style>
