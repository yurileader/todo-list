<template>
  <div class="container-md">
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

      <TodoList
      v-for="t in todos"
      :key="t.id"
      :todo="t"
      @toggle="toggleTodo(t)"
      @remove="excluir(todo)"
    >
    </TodoList>
    
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";

export default {
  name: "App",
  components: { TodoList },
  data() {
    return { todos: [], todo: { checked: false }};
  },
  methods: {
    SalvarTodo(todo) {
      todo.id = Date.now();
      this.todos.push(todo);
    },

    toggleTodo(todo) {
      const index = this.todos.findIndex((item) => item.id === todo.id);

      if (index > -1) {
        const checked = !this.todos[index].checked;
        console.log(checked);
        `${(this.todos[index], { ...(this.todos[index].checked = checked) })}`;
      }
    },

    excluir(todo){
      const index = this.todos.findIndex((item) => item.id === todo.id);

      if (index > -1) {
        this.todos.splice(index, 1)
        
      }
    }
  },
};
</script>

<style scoped>
@import "../node_modules/bootstrap/dist/css/bootstrap.css";

.logo {
  margin-top: 20px;
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
