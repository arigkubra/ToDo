<template>
  <div class="flex flex-col w-72 sm:w-2/5 mx-auto mt-6">
    <TodoList />
    <!-- Bu işlem kalan todo sayısını hesaplar.  -->
    <ResultBar
      :itemCount="todoListData.todoList.length - todoListData.todoList.filter((todo) => todo.completed).length"
    />
    <!-- v-bind kullanarak itemCount'un güncel sayısını ResultBar component'ı içine yazdırabiliyoruz. -->
  </div>
</template>

<script>
import TodoList from "./TodoList.vue";
import ResultBar from "./ResultBar.vue";

export default {
  components: {
    TodoList,
    ResultBar,
  },
  inject: ["todoListData"], // inject kullanarak parent component'ımız olan app.vue'ya erişim sağladık.
  props: {
    //props kullanarak erişim sağladığımız app.vue içinden todoList'imizi çektik.
    todoList: {
      type: Array,
      required: true,
    },
  },
  
};
</script>