<template>
  <div>
    <h2>To do list</h2>
    <p>2023-07-29</p>

    <div id="container">
      <input type="text" v-model="inputValue">
      <button @click.prevent="addEvent()">Add Event</button>
      <div id="doList">
        <div v-for="item in filteredDoList" :key="item.id" :class="{ done: item.done }">
          <input type="checkbox" v-model="item.done">{{ item.text }}
          <button @click="removeEvent(item.id)">X</button>
        </div>
      </div>
    </div>
    <button @click="isShowDoneEvent = !isShowDoneEvent">{{isShowDoneEvent === true ? "Show" : "Hide"}} Done Events</button>
  </div>
</template>

<script setup>
import { computed, ref } from 'vue';

const inputValue = ref("")
const doList = ref([])
const isShowDoneEvent = ref(true)
const filteredDoList = computed(() => {
  return isShowDoneEvent.value === true ? 
  doList.value :
  doList.value.filter(event => { return event.done !== true})
})

function addEvent() {
  doList.value.push({ id: doList.value.length, text: inputValue.value, group: "", done: false })
  inputValue.value = ""
}

function removeEvent(id) {
  doList.value = doList.value.filter(event => { return event.id !== id })
}

</script>

<style>
.done {
  text-decoration: line-through;
}
</style>