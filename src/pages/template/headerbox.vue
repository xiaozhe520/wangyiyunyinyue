<template>
  <div class="headerbox">
    <div class="left-myself">
      <router-link to="">
        <img src="http://112.74.49.105/static/wyy-music/icons/list.png" alt="" class="myself-img" mode="widthFix">
      </router-link>
    </div>
    <div class="middle-todo">
      <div class="middle video"></div>
      <div
      class="middle"
      v-for="(item, index) in headerArr"
      :key="index"
      :data-id="item.id">
        <router-link
        :to="item.path"
        :class="item.className"
        @click.native='changeClass(index)'>
          {{item.title}}
        </router-link>
      </div>
      <div class="middle video"></div>
    </div>
    <div class="right-search">
      <router-link to="">
        <img src="http://112.74.49.105/static/wyy-music/icons/search.png" alt="" class="search-img" mode="widthFix">
      </router-link>
    </div>
  </div>
</template>

<style>
.todo-btn{
  text-decoration: none;
  color: darkgray;
}
.todo-btn-true{
  text-decoration: none;
  color: black;
  font-size: 19px;
  font-weight: 800;
  padding-top: 8px;
}
.search-img{
  width: 50%;
  /* height: 20px; */
  float: right;
  padding-top: 10px
}
.myself-img{
  width: 50%;
  /* height: 20px; */
  float: left;
  padding-top: 10px
}
.headerbox{
  overflow: hidden;
  width: 100%;
  height: 0;
  padding-bottom: 10%;
}
.left-myself{
  overflow: hidden;
  width: 10%;
  height: 0;
  padding-bottom: 10%;
  float: left;
}
.middle-todo{
  overflow: hidden;
  width: 80%;
  height: 0;
  padding-bottom: 10%;
  float: left;
}
.right-search{
  overflow: hidden;
  width: 10%;
  height: 0;
  padding-bottom: 10%;
  float: left;
}
.middle{
  margin-top: 10px;
  overflow: hidden;
  width: 16.6%;
  height: 0;
  padding-bottom: 13%;
  float: left;
  text-align: center;
}
</style>

<script>
export default {
  name: 'header-box',
  data () {
    return {

    }
  },
  methods: {
    changeClass: function (index) {
      this.$emit('changeClass', index)
    }
  },
  props: ['headerArr']
}
</script>
