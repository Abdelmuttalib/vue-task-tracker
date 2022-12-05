<script>
import Tasks from "./components/Tasks.vue";

export default {
  name: "App",
  components: {
    Tasks,
  },
  data() {
    return {
      tasks: [],
    };
  },
  created() {
    this.tasks = [
      {
        id: 1,
        title: "Work on Side Project",
        day: "Monday at 4 pm",
      },
      {
        id: 2,
        title: "Finish PWA Course",
        day: "Wednesday at 3 pm",
      },
      { id: 3, title: "Exercise", day: "Everyday at 9 am" },
    ];
  },

  methods: {
    deleteTask(id) {
      this.tasks = this.tasks.filter((task) => task.id !== id);
    },
  },
};
</script>

<template>
  <main class="w-full h-screen flex justify-center py-40">
    <Tasks @delete-task="deleteTask" :tasks="tasks" />
  </main>
</template>
