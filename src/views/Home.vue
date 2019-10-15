<template>
  <div id="app">
    <AddTodo @add-todo='addTodo'/>
    <Todos :todos='todos' @del-todo='handleDelete'/>
    <router-view/>
  </div>
</template>


<script>
import Header from '../layout/Header'
import AddTodo from '../components/AddTodo'
import Todos from '../components/Todos'

export default {
  name: 'app',
  components: {
    Header,
    Todos,
    AddTodo
  },
  data(){
    return {
      todos:[
        {
          id: 1,
          title: 'Learn VueJS',
          complete: false 
        },
        {
          id: 2,
          title: 'Learn React',
          complete: false
        }
      ]
    }
  },
  methods:{
    handleDelete(id){
      this.todos=this.todos.filter(todo=>todo.id!==id)
    },
    addTodo(newTodo){
      this.todos=[...this.todos, newTodo]
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
  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
</style>
