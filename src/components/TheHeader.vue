<template>
  <header class="header">
    <h1>todos</h1>
    <input
      class="new-todo"
      autofocus
      autocomplete="off"
      placeholder="What needs to be done?"
      v-model="newTodo"
      @keyup.enter="addTodo"
    />
  </header>
</template>
<script>
export default {
  data() {
    return {
      newTodo: ""
    };
  },
  name: "TheHeader",
  methods: {
    addTodo: function() {
      if (!this.newTodo) {
        return;
      }
      this.$store.commit("addTodo", {
        title: this.newTodo,
        completed: false
      });
      this.newTodo = "";
    }
  }
};
</script>
