<template>
  <div class="flex flex-col justify-center items-center">
    <h1 class="font-bold text-3xl pt-10 pb-7 text-white">Todo App</h1>

    <!-- Input Area -->

    <div class="form-control mb-5 w-full max-w-xs">
      <label class="label">
        <span class="label-text text-white">New ToDo</span>
      </label>
      <input
        @keydown.enter="addNewTodo"
        type="text"
        placeholder="Enter Task..."
        class="input input-bordered w-full max-w-xs"
      />
    </div>
  </div>


</template>

<script>
export default{
    components: 'AddSection'
}

</script>