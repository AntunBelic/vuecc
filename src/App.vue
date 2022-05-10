<template>
  <div id="app">
    <TodosComponent v-bind:todos="todos" v-on:del-todo="deleteTodo" v-on:mark-completed="markTodo"/>
    <AddTodo v-on:add-todo='addTodo'/>
  </div>
</template>

<script>
import TodosComponent from "./components/TodosComponent.vue"
import AddTodo from "./components/AddTodo.vue"

export default {
  name: 'App',
  components: {
    TodosComponent,
    AddTodo
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
          completed:true
        },
        {
          id:3,
          title:"Todo Three",
          completed:false
        }
      ]
    }
  },
  methods:{
    deleteTodo(id){
      this.todos=this.todos.filter(todo=>todo.id !== id)
    },
    markTodo(id){
      this.todos = this.todos.map(todo => todo.id === id ? {...todo,completed:!todo.completed}:todo )
    },
    addTodo(newTodo){
      this.todos = [...this.todos,newTodo]
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
.btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }
  .btn:hover {
    background: #666;
  }
</style>
