<template>
  <div class="container">
    <div class="logo">
      <img
        id="logoTodo"
        class="img-fluid"
        src="../src/assets/logo.png"
        alt="Logo marca Todo"
      />
    </div>
    <form @submit.prevent="SalvarTodo(todo)">
      <div class="input-group mt-5">
        <input
          type="text"
          v-model="todo.descricao"
          class="form-control text-center"
          placeholder="Adicione atividades na lista "
        />
        <button class="btn btn-primary" type="submit" id="adicionar">
          Adicionar
        </button>
      </div>
    </form>
    <div class="a grid mt-5">
      <div class="d-flex justify-content-center" v-for="t in todos" :key="t.id">
        <div class="">
          <i class="bi bi-clock "></i>
        </div>
        <div class="ps-3 col-8 d-flex">
          <p>{{ t.id}}</p>
          <p>{{ t.descricao }}</p>
        </div>
        <div class="col-2">
          <button type="button" class="btn  link-danger" id="concluir">
          Concluir
        </button>
        <button type="button" class="btn link-primary ms-1" id="excrluir">
          Excluir
        </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return { todos: [], todo: { checked: false, descricao: "" } };
  },
  methods: {
    SalvarTodo(todo) {
      todo.id = Date.now();
      this.todos.push(todo);
    },
  },
};
</script>

<style scoped>
@import "../node_modules/bootstrap/dist/css/bootstrap.css";

.logo {
  display: flex;
  align-items: center;
  justify-content: center;
}
#logoTodo {
  width: 90px;
  height: 90px;
  align-content: center;
}
</style>
