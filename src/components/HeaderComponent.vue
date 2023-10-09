<template>
    <div id="headerRoot">
        <div class="inputBox">
            <p class="hintText">请在此输入待办事项：</p>
            <input id="inputItem" @keydown.enter="addItem" v-model=eventText placeholder="事件名称">
        </div>
        
    </div>
</template>


<script>
import {nanoid} from 'nanoid'
export default{
    name: 'HeaderComponent',
    data(){
        return{
            eventText:""
        }
    },
    methods:{
        addItem: function(e){
            if (e.target.value==""){
                return;
            }
            console.log(e.target.value);
            const todo = {id:nanoid(), name:e.target.value, done: false}
            this.receive(todo);
            this.eventText="";
        }
    },
    props:['receive']

}
</script>


<style>
.hintText{
    background-color:gainsboro;
    border-radius: 10px;
    flex: 1;
    

}

#headerRoot{
    background-color: gainsboro;
    height: 100px;
}

#inputItem{
    background-color: transparent;
    flex: 1;
}

#inputBox{
    display: flex;
    height: 100%;
    flex-direction: column;
    justify-content: center;
    margin-left: 120px;
    margin-right: 120px;
}

</style>