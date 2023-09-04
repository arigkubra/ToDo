todoItem.vue
<template>
  <li class="flex justify-between items-center mt-5 text-white">
    <span 
    v-if="!item.editing"
    class="w-56"
    >{{ item.text }}</span>
    <input
      v-else
      v-model="item.text"
      @blur="saveEdit"
      @keyup.enter="saveEdit"
      class="text-black"
    />
    <button @click="toggleEdit" class="bg-blue-300">
      {{ item.editing ? "Save" : "Edit" }}
    </button>
    <button @click="deleteItem(item)" class="btn btn-sm bg-red-600">
      Delete
    </button>
  </li>
</template>

<script>
export default {
  inject: ["deleteItem"],
  props: ["item"],
  methods: {
    toggleEdit() {
      // Düzenleme modunu ters çevir (true ise false, false ise true)
      this.item.editing = !this.item.editing;
    },
    saveEdit() {
      this.toggleEdit(); // Düzenleme modunu kapat
    },
  },
};
</script>
