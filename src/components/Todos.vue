<template>
  <div class="container">
    <input type="text"

     placeholder="add todo"
     v-model="todo"
     @keyup.enter="addTodo"
       >

       <div class="todos">
       	<ul>
       		<li v-for="(todo,index) in todoList">
       		<span :class="{completed:todo.done}">
       			<input type="checkbox" v-model="todo.done">
       		    {{todo.name}}
       		</span>
       		</li>
       	</ul>
       	<footer>
       		<span class="all" @click.prevent ="allTodos">All</span>
       		<span class="done" @click.prevent="isDone">Done</span>
       		<span class="todo" @click.prevent = "toDo">Todo</span>
       	</footer>
       </div>
  </div>
</template>

<script>
export default {
  name: 'Todos',
  data () {
    return {
      todo: '',
      todoList:[],
      checked :false
     
    }
  },
  // -----------------------------
  methods:{
  	addTodo:function(){
  		this.todoList.push({name:this.todo,done:false})
  	},
  	isDone:function(){
  		this.todoList = this.todoList.filter(x =>x.done === true)
  	},
  	allTodos :function(){
  	  this.todoList = this.todoList
  	},
  	toDo:function(){
    this.todoList = this.todoList.filter(x => x.done === false)
  	}

 

  }
};
</script>


