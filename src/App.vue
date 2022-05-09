<template>
  <div id="app">
    <TodosComponent v-bind:todos="todos"/>
  </div>
</template>

<script>
import TodosComponent from "./components/TodosComponent.vue"

export default {
  name: 'App',
  components: {
    TodosComponent
},
  data(){
    return {
      todos:[
        {
          id:1,
          title:"Todo One",
          completed:false
        },
        {
          id:2,
          title:"Todo Two",
          completed:false
        },
        {
          id:3,
          title:"Todo Three",
          completed:false
        }
      ]
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
</style>
