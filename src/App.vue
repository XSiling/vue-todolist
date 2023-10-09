<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- //<HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <div id="appRoot">
    <HeaderComponent :receive="receive"></HeaderComponent>
    <hr>
    <ListComponent :todoList="todoList" :handleCheck="handleCheck" :deleteTodo="deleteTodo"></ListComponent>
    <hr>
    <FooterComponent></FooterComponent>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import HeaderComponent from './components/HeaderComponent.vue'
import ListComponent from './components/ListComponent.vue'
import FooterComponent from './components/FooterComponent.vue'

export default {
  name: 'App',
  components: {
    HeaderComponent,
    ListComponent,
    FooterComponent
  },
  data(){
    return{
      todoList:[
                {id:'001', name:"学习Vue", done: false},
                {id:'002', name:"刷leetcode", done: false},
                {id:'003', name:"投简历", done: false}
            ]
    } 
  },
  methods:{
    receive(x){
      console.log(x);
      this.todoList.unshift(x);
    },
    handleCheck(id){
      this.todoList.forEach((todo)=>{
        if (todo.id ===id ) todo.done =!todo.done;
      })
    },
    deleteTodo(id){
      this.todoList = this.todoList.filter((todo)=>{
        return todo.id !== id;
      })
    }
  }
}
</script>

<style>
#appRoot{
  /* background-color: gray; */
  background-color: lightcyan;
}
</style>
