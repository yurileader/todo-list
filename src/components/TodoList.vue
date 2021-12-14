<template>
  <div class="hello">
   <ul class="list-group">
  <li v-for="todos in listaTodos" :key="todos.id" :itemprop="todo" class="list-group-item list-group-item-dark">{{todos.descricao}} {{todos.descricao}}</li>
</ul>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  props: {
    listaTodos: [],
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
