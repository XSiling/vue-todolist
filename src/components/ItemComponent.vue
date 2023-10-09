<template>
    <div id="rootItem">
        <div :class="todoEventStyle" >
            <input type="checkbox" name="done" @click="changeCheckBox(todo.id)" :checked="todo.done">
            {{ todo.name }}
            <button class="btn btn-danger" @click="deleteItem(todo.id)">删除</button>
        </div>

    </div>
</template>


<script>
export default{
    name: 'ItemComponent',
    data(){
        return {
            todoEventStyle: "todoEvent"
        }
    },
    props:['todo',"handleCheck", "deleteTodo"],
    methods:{
        changeCheckBox(id){
            //console.log(e);
            //console.log(e.target.checked);
            // if (e.target.checked){
            //     this.todoEventStyle = "todoEventChecked";
            // }else{
            //     this.todoEventStyle = "todoEvent"
            // }
            if (this.todoEventStyle == "todoEvent"){
                this.todoEventStyle = "todoEventChecked";
            }else{
                this.todoEventStyle = "todoEvent";
            }
            this.handleCheck(id);
        },
        deleteItem(id){
            if (confirm("确定删除？")){
                console.log(id);
                this.deleteTodo(id);
            }
        }
    }
}
</script>

<style>


.todoEventChecked{
    text-decoration: line-through;
    color: gray;
}

#rootItem:hover{
    background-color:green;
}

button{
    display:none;
    float:right;
    margin-right:50px;
}

#rootItem:hover button{
    display: block;
}
</style>