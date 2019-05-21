<template>
  <div id="app">
    <header-box :headerArr="headerArr" @changeClass="changeClass"></header-box>
    <router-view/>
  </div>
</template>

<script>
import header from './pages/template/headerbox.vue'

export default {
  name: 'App',
  data () {
    return {
      headerArr: [
        {'title': '我的', 'id': 0, 'path': '', 'className': 'todo-btn-true'},
        {'title': '发现', 'id': 1, 'path': '', 'className': 'todo-btn'},
        {'title': '朋友', 'id': 2, 'path': '', 'className': 'todo-btn'},
        {'title': '视频', 'id': 3, 'path': '', 'className': 'todo-btn'}
      ]
    }
  },
  components: {
    'header-box': header
  },
  methods: {
    changeClass (index) {
      for (var i = 0; i < this.headerArr.length; i++) {
        if (index === i) {
          console.log(index)
          this.headerArr[i].className = 'todo-btn-true'
        } else {
          this.headerArr[i].className = 'todo-btn'
        }
      }
      console.log(this.headerArr)
    }
  }
}
</script>

<style>

</style>
