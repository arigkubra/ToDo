<template>
  <div class="bg-zinc-800 h-screen">
    <h1
      class="flex flex-col justify-center items-center font-bold text-3xl pt-10 pb-7 text-white"
    >
      Todo App
    </h1>

    <AddSection :addItem="addItem" />

    <ListSection />
  </div>
</template>

<script>
import AddSection from "./components/AddSection.vue";
import ListSection from "./components/ListSection.vue";
export default {
  data(){
    return{
      getData: {
        todoList: [
          { id: 1, text:"First Todo" },
          { id: 2, text:"Second Todo" },
        ]
      }
    }
  },
  provide(){
    return{
      getData: this.getData,
      deleteItem : this.deleteItem
    }
  },
  components: {
    AddSection,
    ListSection,
  },
  methods: {
    addItem(todo) {
      this.getData.todoList.push({
        id: new Date().getTime(), //unique bir değer oluşturmak için şu anki saati ve tarihi milisaniye cinsinden bir sayıya dönüştürür. Id oluşturmak için kullanılır.
        text: todo,
        });
      },
    clearAll(todoList){
      
    },
    deleteItem(todoItem) {
      this.getData.todoList = this.getData.todoList.filter((t) => t != todoItem)
      }
    },
    
 
  
};
</script>


