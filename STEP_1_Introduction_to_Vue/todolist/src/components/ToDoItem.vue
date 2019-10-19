<template>
  <li class="item" @click="handleClick">{{content}}</li>
</template>

<script>
export default {
 props: ['content', 'index'],
 methods: {
  handleClick: function(index) {
    this.$emit('delete', index)
  } 
 }
};
</script>


<style scoped>
.item {
  color: green;
}


</style>
