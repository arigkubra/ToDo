<template>
  <div class="bg-zinc-800 h-screen">

    <div class="flex flex-col justify-center items-center ">

      <h1 class="font-bold text-3xl pt-10 pb-7 text-white">Todo App</h1>

      <!-- Input Area -->

      <div class="form-control mb-5 w-full max-w-xs">
        <label class="label">
          <span class="label-text text-white">New ToDo</span>
        </label>
        <input
          type="text"
          placeholder="Enter Task..."
          class="input input-bordered w-full max-w-xs"
        />
      </div>
    </div>

    <!-- Buttons -->
    
    <div class="flex justify-center items-center">
      
      <buttons class="btn-neutral">Clear Todos</buttons>
      <buttons class="ml-10 btn-primary">Add Todos</buttons>
      
    </div>
    
    <TodoItem />
  </div>
</template>

<script>
import TodoItem from "./components/TodoItem.vue";
import Buttons from "./components/Buttons.vue";
export default {
  name: "App",
  components: {
    TodoItem,
    Buttons,
  },
};
</script>


