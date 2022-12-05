<script>
import Task from "./Task.vue";

export default {
  name: "Tasks",
  components: {
    Task,
  },
  props: {
    tasks: Array,
  },
};
</script>

<template>
  <div class="flex flex-col gap-20 w-full max-w-sm">
    <header>
      <h1 class="text-5xl font-semibold text-center">Task Tracker</h1>
    </header>

    <section class="flex flex-col gap-3">
      <div v-for="task in tasks">
        <Task @delete-task="$emit('delete-task', task.id)" :task="task" />
      </div>
    </section>
  </div>
</template>
