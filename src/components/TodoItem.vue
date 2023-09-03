<template>
  <li class="flex justify-between items-center mt-5">
    <span>{{ item.text }}</span>
    <button
    @click="deleteItem(item)" 
    class="btn btn-sm bg-red-600"
    >Delete</button>
  </li>
</template>

<script>
export default {
  inject:["deleteItem"],
  props:["item"],
};
</script>