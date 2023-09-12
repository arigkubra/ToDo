todolist.vue
<template>
    <ul class="flex flex-col justify-center">
        <TodoItem 
            class="text-white"
            v-for="todoItem in todoListData.todoList"
            :key="todoItem.id"
            :item="todoItem"
        
        />
    </ul>

    
</template>
<script>

import TodoItem from './TodoItem.vue';
export default{
    inject:["todoListData"],
    components:{
        TodoItem,
    }
    
}


</script>
