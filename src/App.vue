<template>
  <div 
    class="bg-indigo-300 min-h-screen sm:min-h-0 sm:h-screen sm:w-full sm:text-base text-sm">
  

    <h1
      class="flex flex-col justify-center items-center font-bold text-3xl pt-10 pb-7 text-white"
    >
      Todo App
    </h1>

    <AddSection :addItem="addItem" :clearAllHandler="clearAll" />

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
        todoList: []
      }
    }
  },
  provide(){
    return{
      getData: this.getData,
      deleteItem : this.deleteItem,
    }
  },
  components: {
    AddSection,
    ListSection,
  },
  methods: {
    addItem(todo) {
      if(!todo){
        alert("Please don't enter empty todo!")
      }
      
      else{
        this.getData.todoList.push({
        id: new Date().getTime(), //unique bir değer oluşturmak için şu anki saati ve tarihi milisaniye cinsinden bir sayıya dönüştürür. Id oluşturmak için kullanılır.
        text: todo,
        });
      }
      
      },
      clearAll(todoList) {
      this.getData.todoList = [];
      console.log("test");
    },
    
    deleteItem(todoItem) {
      this.getData.todoList = this.getData.todoList.filter((t) => t != todoItem)
      }
    },
    
    
    
 
  
};
</script>