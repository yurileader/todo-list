<template>
  <div class="a grid mt-5" :class="{checked: todo.checked}">
      <div class="d-flex justify-content-center" >
        <div class="">
          <i class="bi  " :class="todo.checked ? 'bi-check2' : 'bi-clock' " ></i>
        </div>
        <div class="ps-3 col-8 d-flex">
          <p>{{ todo.descricao }}</p>
        </div>
        <div class="col-2">
          <button @click="$emit('toggle', todo)" type="button" class="btn  link-danger" id="concluir">
            <span v-if="todo.checked">Desmarcar</span>
            <span v-else>Concluir</span>
        </button>
        <button  type="button" class="btn link-primary ms-1" id="excrluir">
          Excluir
        </button>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: "TodoList",
  props: {
    todo: {type: Object}
  },
};
</script>

<style scoped>
.checked{
  text-decoration: line-through;
  color: lightgray;
}
</style>
