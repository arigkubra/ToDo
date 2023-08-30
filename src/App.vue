<template>
  <div class="bg-zinc-800 h-screen">

    <AddSection />


    <!-- Buttons -->

    <div class="flex justify-center items-center">
      <buttons class="btn-neutral">Clear Todos</buttons>
      <buttons class="ml-10 btn-primary">Add Todos</buttons>
    </div>

    <TodoItem />
  </div>
</template>

<script>
import AddSection from "./components/AddSection.vue";
import TodoItem from "./components/TodoItem.vue";
import Buttons from "./components/Buttons.vue";
export default {
  name: "App",
  components: {
    AddSection,
    TodoItem,
    Buttons,
  },
  methods: {
    addNewTodo(e) {
      console.log(event.target.value);
    },
  },
};
</script>


