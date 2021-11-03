<template>
  <div class="hello">
    <form @submit.prevent="addTodo">
      <input type="text" v-model="inputTodo"/>
      <button type="submit">ADD</button>
    </form>

    <div>
      <ul>
        <li v-for="(todo,index) in todolists" :key="index">
          {{todo}} <span v-on:click="remove(index)">x</span>
        </li>
      </ul>
    </div>
    
    
  </div>
</template>

<script>
export default {
  name: 'Todo',
  data(){
    return{
      inputTodo: '',
      todolists: []
    }
  },
  methods:{
    addTodo(){
      this.todolists.push(this.inputTodo);
      this.inputTodo = "";
    },
    remove(id){
      const newTodo = this.todolists.filter((el,index) => index !== id);
      this.todolists = newTodo;
    }
  }
}
</script>


<style scoped>

</style>
