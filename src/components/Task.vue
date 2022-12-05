<script>
import { XMarkIcon } from "@heroicons/vue/20/solid";

export default {
  name: "Task",
  props: {
    task: Object,
  },
  components: {
    XMarkIcon,
  },
};
</script>

<template>
  <div
    class="flex flex-col gap-1 w-full px-6 py-4 border rounded border-gray-600 hover:border-gray-500"
  >
    <div class="flex justify-between">
      <h3 class="text-lg font-semibold">{{ task.title }}</h3>

      <XMarkIcon
        @click="$emit('delete-task', task.id)"
        class="w-5 text-red-400 cursor-pointer hover:text-red-300"
      />
    </div>
    <p class="text-gray-500 font-medium">{{ task.day }}</p>
  </div>
</template>
