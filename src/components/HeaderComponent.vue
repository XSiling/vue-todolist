<template>
    <div id="headerRoot">
        <div class="inputBox">
            <p class="hintText">请在此输入待办事项：</p>
            <input id="inputItem" @keydown.enter="addItem" v-model=eventText>
        </div>
        
    </div>
</template>


<script>
export default{
    name: 'HeaderComponent',
    data(){
        return{
            eventText:"这是一个默认事件"
        }
    },
    methods:{
        addItem: function(e){
            console.log(e);
            console.log("?");
        }
    }

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