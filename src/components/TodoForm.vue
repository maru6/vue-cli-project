<template>
  <form v-on:submit.prevent="addTodo(newTodo)">
      <div class="from-group">
          <input type="text"
                 v-model="newTodo.title"
                 class="form-control"
                 placeholder="Add a new todo">
      </div>
      <br>
      <div class="form-group">
          <button class="btn btn-success" type="submit">Add Todos</button>
      </div>
  </form>
</template>

<script>
export default {
      props:['todos'],
      data(){
        return {
            newTodo:{id:null,title:'', completed:false}
        }
      },
      methods:{
          addTodo(newTodo){
              this.todos.push(newTodo),
              this.newTodo = {id:null,title:''}
          }
      }
}
</script>

<style>
  .completed {
    color: #5cb85c;
    text-decoration: line-through;
  }
  .margin-right-10 {
    margin-right: 10px;
  }

</style>
