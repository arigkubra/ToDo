todoItem.vue
<template>
  <li class="flex justify-around items-center mt-5  text-white">
    <span 
    v-if="!item.editing"
    >{{ item.text }}</span>
    <input
      v-else
      v-model="item.text"
      @blur="saveEdit"
      @keyup.enter="saveEdit"
      class="text-black"
    />
    <buttons @click="deleteItem(item)" class="btn btn-sm bg-red-600">Delete</buttons> 
    <buttons @click="toggleEdit" class="btn btn-sm bg-blue-300">{{ item.editing ? "Save" : "Edit" }}</buttons>
    
  </li>
</template>

<script>
import Buttons from './Buttons.vue';
export default {
  inject: ["deleteItem"],
  props: ["item"],
  components:{
    Buttons,
  },
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
