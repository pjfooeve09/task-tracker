<template>
  <div :key="t.id" v-for="t in tasks "> 
    <TaskComponent :task="t" @toggle-reminder="$emit('toggle-reminder', t.id)" @delete-this-task="$emit('delete-task', t.id)" />  
  </div>
</template>

<script>

import TaskComponent from './Task'

export default {
  name: 'TasksComponent',
  props: {
    tasks: Array
  },
  components: {
    TaskComponent
  },
  emits: ['delete-task', 'toggle-reminder'] 
}
</script>

