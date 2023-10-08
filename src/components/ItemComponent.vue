<template>
    <div id="root">
        <div :class="todoEventStyle" >
            <input type="checkbox" name="done" @click="changeCheckBox" :checked="todo.done">
            {{ todo.name }}
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
    props:['todo'],
    methods:{
        changeCheckBox(e){
            //console.log(e);
            //console.log(e.target.checked);
            if (e.target.checked){
                this.todoEventStyle = "todoEventChecked";
            }else{
                this.todoEventStyle = "todoEvent"
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
</style>