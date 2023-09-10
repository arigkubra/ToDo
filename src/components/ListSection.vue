<template>
    <div class="flex flex-col w-72 sm:w-2/5 mx-auto  mt-6">
        <TodoList />
        <ResultBar :itemCount="getData.todoList.length" />
        <!-- v-bind kullanarak itemCount'un güncel sayısını ResultBar component'ı içine yazdırabiliyoruz. -->
    </div>
</template>

<script>
import TodoList from './TodoList.vue'; 
import ResultBar from './ResultBar.vue'; 


export default{
    components:{
        TodoList,
        ResultBar,
    },
    inject: ["getData"], // inject kullanarak parent component'ımız olan app.vue'ya erişim sağladık.
    props:{ //props kullanarak erişim sağladığımız app.vue içinden todoList'imizi çektik.
        todoList:{
            type: Array,
            required: true
        }
    }
}

</script>