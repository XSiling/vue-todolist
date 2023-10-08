<template>
    <div id="root">
        <div id="defaultItem" :class="defaultItemStyle">
            <ItemComponent></ItemComponent>
        </div>
        
        <ul class="todo-main">

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
            todoList:[]
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
    }
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

</style>