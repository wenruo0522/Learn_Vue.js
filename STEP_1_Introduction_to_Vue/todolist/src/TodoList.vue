<template>
  <div>
    <input v-model="inputValue">
    <button @click="handleClick">submit</button>
    <ul> 
      <todo-list v-for="(item, index) in list"
      :key="index"
      :content="item"
      :index="index"
      @delete="handleDelete"   
      > 
      </todo-list>  
    </ul>
  </div>
</template>

<script>
import ToDoItem from './components/ToDoItem'
export default {
  components: {
    'todo-list': ToDoItem
  },
  data: function() {
    return {
      inputValue: '',
      list: []
    }
  },
  methods: {
    handleClick: function() {
      this.list.push(this.inputValue)
      this.inputValue = ''
    },
    handleDelete: function(index) {
      this.list.splice(index, 1)
    }
  }
};
</script>

<style>

</style>
