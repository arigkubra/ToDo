<template>
  <div class="flex flex-col justify-center items-center">
    

    <!-- Input Area -->

    <div class="form-control mb-5 w-full max-w-xs">
      <label  class="label">
        <span class="label-text text-white">New ToDo</span>
      </label>
      <!-- Inputtan gelecek olan verilere todoText adını veriyorum. -->
      <input
        
        v-model="todoText" 
        id="todoText"
        type="text"
        placeholder="Enter Task..."
        class="input input-bordered w-full max-w-xs"
      />
    </div>
    
    <!-- Buttons -->

    <div class="flex justify-center items-center">
<!-- Burada ise click event'i tetiklendiğinde addITem fonksiyonunu çalıştır ve argüman olarak inputtan gelen todoText'i vermesini sağlıyorum -->
      <button 
      @click="clearAllHandler"
      class="btn btn-neutral">Clear Todos</button>
      <button @click="addItem(todoText);
       clearInput()" 
       class="ml-10 btn btn-primary"  >
       Add Todos
      </button>


    </div>
  </div>


</template>

<script>
export default{
    data(){
      return{
        todoText: null,
        
      }
    },
    props:{ // addItem fonksiyonunu kullanabilmek için props olarak çekmemiz gerekiyor.
      addItem:{
        type: Function,
        required: true
      },
      todoList:{
        type: Array,
        required: true
      },
      // clearAll:{
      //   type: Function,
      //   required: true
      // },
      clearAllHandler:{
        type: Function,
      },
      
    },
    methods:{
      clearInput(){
        this.todoText = null;
      },
      clearAll(){
      this.todoList = [];
      console.log("Tüm todolar silindi!");
    },
      
    }
}

</script>