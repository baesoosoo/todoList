<template>
  <div id="app" class="container">
    <h1 class="text-center">Todo App</h1>
      <input  
          v-model="todoText"
          type="text" 
          class="w-100 p-2" 
          placeholder="Type todo"
          @keyup.enter="addTodo">
      <hr>
      <MyTodolist v-for="todo in todos" :key="todo.id" :todo="todo" />
    
     
  </div>
</template>

<script>
import MyTodolist from '@/components/MyTodolist.vue';

export default {
  components:{
    MyTodolist
  },
  data(){
    return {
      todoText:'',
      todos:[
        { id: 1, text: 'buy a car',checked: false},
        { id: 2, text: 'play game',checked: false},
      ]
    }
  },
  methods: {
    addTodo(e){
      this.todos.push({
        id:Math.random(),
       text: e.target.value,
       checked:false
      });
      this.todoText ='';
    }
  }
}
</script>

