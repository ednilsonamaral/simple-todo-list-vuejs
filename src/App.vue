<template>
  <div id="app">
    <h1>ToDo List</h1>

    <input type="text" v-model="text" v-on:keyup.enter="addTodo()">

    <ul>
        <li v-for="item in list">
            <!-- <span>{{ item.text }}</span> -->
            <!-- <button @click="removeTodo($index)" style="cursor: pointer;">X</button> -->
            <todo-item v-bind:item="item" @remove="removeTodo($index)"></todo-item>
        </li>
  </div>
</template>

<script>
import TodoItem from './todo-item.vue';

export default {
  data () {
    return {
        list: [{ text: 'Adicionar mais itens a lista' }],
        text: ''
    }
  },

  components: { TodoItem },

  methods: {
      addTodo() {
          this.list.push({ text: this.text })
          this.text = ''
      },

      removeTodo(index) {
          this.list.splice(index, 1)
      }
  }
}
</script>

<style>
body {
  font-family: Helvetica, sans-serif;
}
</style>
