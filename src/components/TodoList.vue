<template>
    <ul>
        <TodoItem 
            class="text-white"
            v-for="todoItem in getData.todoList"
            :key="todoItem.id"
            :item="todoItem"
        
        />
    </ul>

    
</template>
<script>
import { inject } from 'vue';
import TodoItem from './TodoItem.vue';
export default{
    inject:["getData"],
    components:{
        TodoItem,
    }
    
}


</script>



<!-- <div class="overflow-x-auto w-96 text-white">
    <table class="table">
      <tbody>
        <tr>
          <div class="form-control ">
            <label class="cursor-pointer label">
              <span class="label-text text-white">{{ item }}</span>
              <input
                type="checkbox"
                
                class="checkbox checkbox-warning"
              />
            </label>
          </div>
        </tr>
      </tbody>
    </table>
  </div> -->