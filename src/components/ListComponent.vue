<template>
    <div id="root">
        <!-- <div id="defaultItem" :class="defaultItemStyle">
            <ItemComponent></ItemComponent>
        </div> -->
        
        <ul class="todo-main">
            <ItemComponent v-for="todo in todoList" :key="todo.id" :todo="todo" :handleCheck="handleCheck" :deleteTodo="deleteTodo"></ItemComponent>
        </ul>
    </div>

</template>


<script>
import ItemComponent from './ItemComponent.vue';

export default{
    name: 'ListComponent',
    data(){
        return {
            defaultItemStyle: "displayDefaultItemStyle",

        }
    },
    methods:{
        changeDefaultItemStyle(direction){
            if (direction == 1){
                this.defaultItemStyle = "displayDefaultItemStyle"
            }else{
                this.defaultItemStyle = "notDisplayDefaultItemStyle"
            }
        }
    },
    components:{
        ItemComponent
    },
    props:["todoList","handleCheck","deleteTodo"]
}
</script>

<style>
.displayDefaultItemStyle{
    display: inline-block;
    color: gray;
}

.notDisplayDefaultItemStyle{
    display: None;
}

#todo-main{
    height: 500px;
}

</style>