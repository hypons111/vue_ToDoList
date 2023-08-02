<template>
  <todolist id="todolist"/>
</template>

<script>
import todolist from './components/todolist.vue'

export default {
  name: 'App',
  components: {
    todolist
  },
  data() {
    return {}
  }
}
</script>

<style>

#app {
  height: calc(100vh - 1em);
  margin: 0;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  border: 1px solid blue;
}
#todolist {
  border: 1px solid green;
}
#vueLogo {
  width: 5vw;
}
</style>
