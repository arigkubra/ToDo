<template>
  <li 
    class="flex justify-between  items-center mt-5 bg-indigo-900 rounded-lg p-3  text-white">
    <input 
      type="checkbox"  
      class="checkbox border-slate-300"
      v-model="item.completed"
      />
    <div
    class="whitespace-normal w-full  break-all ml-5"
    :style="{ 'text-decoration': item.completed ? 'line-through' : 'none' }"
    v-if="!item.editing"
    >{{ item.text }}</div>
    <input
      v-else
      v-model="item.text"
      @keyup.enter="saveEdit"
      class="text-black sm:w-full w-3/4 ml-2"
    />
    <div class="flex">
      <buttons @click="toggleEdit" class="btn btn-primary text-white sm:btn-sm ">{{ item.editing ? "Save" : "Edit" }}</buttons>
      <buttons @click="deleteItem(item)" class="btn text-white sm:btn-sm bg-gray-600 hover:bg-red-700">Delete</buttons> 
    </div>
    
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
      // Düzenleme modunun değerini değiştirir. 
      this.item.editing = !this.item.editing;
    },
    saveEdit() {
      this.toggleEdit(); // Düzenleme modunu kapatır.
    },
    
  },
  
};
</script>
