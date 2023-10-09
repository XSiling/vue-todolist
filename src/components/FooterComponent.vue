<template>
    <div id="root">

        <div id="clearDiv">
            <input type="checkbox" name="complete">已完成{{ completeNum }} / 全部{{ allNum }}
            <button name="clearAll">清除已完成任务</button>
        </div>
        
    </div>
</template>


<script>
export default{
    name: 'FooterComponent',
    data(){
        return {
            allNum : this.todoList.length

        }
    },
    props:["todoList"],
    methods:{

    },
    computed:{
        completeNum(){
            let i=0;
            this.todoList.forEach((todo)=>{
                if (todo.done){
                    i ++;
                }
            })
            return i;
        }
    }
}
</script>

<style>
.clearDiv{
    display: inline-block;
    margin-right: 5px;
    position: right;
    padding-left: 10px;
}
</style>