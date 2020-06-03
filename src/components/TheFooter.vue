<template>
  <footer class="footer">
    <span class="todo-count">
      <strong>{{ todosCount }}</strong> 条记录
    </span>
    <ul class="filters">
      <li>
        <router-link to="/all" :class="{ selected: filter === 'all' }"
          >All</router-link
        >
      </li>
      <li>
        <router-link to="/active" :class="{ selected: filter === 'active' }"
          >Active</router-link
        >
      </li>
      <li>
        <router-link
          to="/completed"
          :class="{ selected: filter === 'completed' }"
          >Completed</router-link
        >
      </li>
    </ul>
    <button class="clear-completed" @click="allRemoveTodo()">删除已完成</button>
  </footer>
</template>
<script>
export default {
  name: "TheFooter",
  created() {
    this.fetchFilter();
  },
  watch: {
    $route: "fetchFilter"
  },
  computed: {
    filter() {
      return this.$store.state.filter;
    },
    todosCount() {
      return this.$store.getters.todosCount;
    },
    hasCompleted() {
      return this.$store.getters.hasCompleted;
    }
  },
  methods: {
    allRemoveTodo: function() {
      this.$store.commit("removeCompleted");
    },
    fetchFilter: function() {
      let filter = this.$route.params.filter;
      this.$store.commit("changeFilter", filter);
    }
  }
};
</script>
>
