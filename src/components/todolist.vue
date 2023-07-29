<template>
  <div>
    <h1>To do list</h1>
    <i>2023-07-29</i>

    <div id="container">

      <div id="panel">
        <input type="text" v-model="inputValue">
        <button v-on:click="addEvent()">ADD</button>
      </div>

      <div id="list">
        <div id="todo">
          <h3>ToDo</h3>
          <ol>
            <li v-for="item, index in toDo" :key="item">
              {{ item }} <button v-on:click="removeEvent(index)">X</button>
            </li>
          </ol>
        </div>

        <div id="done">
          <h3>Done</h3>
          <ol>
            <li v-for="item, index in done" :key="item">
              {{ item }} <button v-on:click="removeEvent(index)">X</button>
            </li>
          </ol>
        </div>

      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: "todolist",
  data() {
    return {
      inputValue: "",
      toDo:[],
      done:[]
    }
  },
  methods: {
    dataIncrease() {
      this.dataVeriable ++
    },
    addEvent() {
      this.toDo.push(this.inputValue)
      this.inputValue = ""
    },
    removeEvent(index) {
      this.done.push(this.toDo.splice(index, 1))
    },
    clearInput() {
      this.inputValue = ""
    }
  }
}
</script>

<style>
h1 {
  display: inline-block;
}
i {
  position: absolute;
  top: 1em;
  right: 1em;
} 
#container,
#panel,
#list {
  display: flex;
}
#container {
  flex-flow: column;
  width: 70vw;
  margin: auto;
  border: 1px solid red;
}
#panel {
  justify-content: center;
  border: 1px solid blue;
}
#todo, #done {
  flex-grow: 1;
  border: 1px solid gray;
}
li {
  border: 1px solid gray;
}
</style>