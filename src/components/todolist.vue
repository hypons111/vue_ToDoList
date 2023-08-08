<template>
  <div>
    <h1>To do list</h1>
    <i>2023-07-29</i>

    <div id="container">

      <form @submit.prevent="addEvent()">
        <input type="text" v-model="inputValue">
        <button>ADD</button>
      </form>

      <div id="list">
        <div id="doList">
          <h3>doList</h3>
          <ol>
            <li v-for="item in doList" :key="item.id">
              {{ item.text }} <button @click="removeEvent(item.id)">X</button>
            </li>
          </ol>
        </div>

        <div id="doneList">
          <h3>doneList</h3>
          <ol>
            <li v-for="item in doneList" :key="item">
              {{ item }} <button>X</button>
            </li>
          </ol>
        </div>

      </div>

    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const inputValue = ref("")
const doList = ref([])
const doneList = ref([])

function addEvent() {
  doList.value.push({id: doList.value.length, text: inputValue.value})
  inputValue.value = ""
}

function removeEvent(id) {
  doList.value = doList.value.filter(item => {
    if(item.id === id) {
      doneList.value.push(item.text)
    }
    return item.id !== id
  })
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
#doList, #doneList {
  flex-grow: 1;
  border: 1px solid gray;
}
li {
  border: 1px solid gray;
}
</style>