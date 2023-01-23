<template>
  <div>
    <input type="text" placeholder="タスクを追加" @keyup.enter="addTodo" />
    <ul>
      <li v-for="todo in todos">
        <input
          type="checkbox"
          :checked="todo.done"
          @change="toggle(todo)"
          :key="todo.text"
        />
        <span :class="{ done: todo.done }">{{ todo.text }}</span>
      </li>
    </ul>
  </div>
</template>
<script>
import { mapMutations } from "vuex";
export default {
  methods: {
    addTodo(e) {
      if (e.target.value === "") {
        return;
      }
      this.$store.commit("todos/add", e.target.value);
      e.target.value = "";
    },
    ...mapMutations({
      toggle: "todos/toggle",
    }),
  },
  computed: {
    todos() {
      return this.$store.state.todos.list;
    },
  },
};
</script>
<style>
.done {
  text-decoration: line-through;
}
</style>
