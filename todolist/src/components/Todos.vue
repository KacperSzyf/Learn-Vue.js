<template>
<div v-for="todo in todos" :key="todo.id">
  <TodoItem :todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"
            v-on:mark-complete="todo.completed = $event"/>
<!--'@update' listens to the child component for emitted change, ':todo' is shorthand
 for doing v-binding todo prop to each child element created -->
</div>
</template>

<script>
import TodoItem from "@/components/TodoItem";

export default {
  name: "Todos",
  components: {TodoItem},
  props: ['todos'],
}
</script>

<style scoped>

</style>