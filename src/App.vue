<template>
  
  <VueTest_1 id="todolist" :props-veriable="veriable"/>

  
</template>

<script>
import VueTest_1 from './components/VueTest_1.vue'

export default {
  name: 'App',
  components: {
    VueTest_1
  },
  data() {
    return {
      veriable: "0"
    }
  },
  methods: {
    propsIncrease() {
      this.veriable ++
    }
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
