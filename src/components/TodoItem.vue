<template>
  <div :class="{'is-complete':todo.completed}">
    <p>
      <input type="checkbox" @change="markComplete" />
      {{todo.title}}
      <button @click="$emit('del-todo', todo.id)">x</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed ^= true;
    }
  }
};
</script>

<style scoped>
.is-complete {
  text-decoration: line-through;
}
</style>