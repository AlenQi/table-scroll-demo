<template>
  <div id="app" class="content">
    <h1>方式一：鼠标在哪一行，就滚动哪里，如果子table滚动条部到底了，父级滚动条会滑动</h1>
    <Table1 />
    <h1>方式二：子table如果展开，可以扩宽父级table的宽度，子table和父table整体滚动</h1>
    <Table2 />
  </div>
</template>

<script>
import Table1 from './components/Table1.vue'
import Table2 from './components/Table2.vue'

export default {
  name: 'App',
  components: {
    Table1,
    Table2,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.content {
  width: 1200px;
  overflow: scroll;
  border: 1px saddlebrown solid;
  padding: 20px;
}
</style>
