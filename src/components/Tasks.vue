<template>
  <div v-for="task in tasks" :key="task.id">
    <Task
    @delete-task="$emit('delete-task', task.id)"
    @toggle-reminder="$emit('toggle-reminder', task.id)"
    :task="task"/>
  </div>
</template>

<script>
import Task from './Task'

export default {
  name: 'Tasks',
  components: {
    Task
  },
  props: {
    tasks: Array
  },
  emits: ['delete-task', 'toggle-reminder']
}
</script>