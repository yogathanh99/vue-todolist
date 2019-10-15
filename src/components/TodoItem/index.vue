<template>
  <div class="todo-item" :class="{'is-complete': todo.complete}">
    <p>
      <input type='checkbox' @change='handleChange' :checked='todo.complete'>
      {{todo.title}}
      <button class='del' @click="$emit('del-todo', todo.id)">X</button>
      </p>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['todo'],
  methods:{
    handleChange(){
      this.todo.complete=!this.todo.complete
    }
  }
}
</script>

<style scoped>
  .todo-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
  }

  .is-complete {
    text-decoration: line-through;
  }

  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
  }
</style>