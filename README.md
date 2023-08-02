# To Do List


## 元件使用方法
### 子元件 :
存放在 components 資料夾內

### 父元件 :

#### 載入
```
import todolist from './components/todolist.vue'
```
#### 註冊
```
export default { 
    components: { todolist } 
}
```
#### 使用
```
<template>
    <todolist id="todolist"/>
</template>
```

## v-model="inputValue"
只可以放在 <input>, <textarea>, <select>
綁定 data() {} 中的變數 

## v:on:click="addEvent()"
呼叫 mehtods: {} 中的方法

## v-for="item, index in done" :key="item"
done 是要 loop 的列陣