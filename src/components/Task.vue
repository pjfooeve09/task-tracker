<template>
  <div :class="[task.reminder ? 'reminderrr' : '', 'task']" @dblclick="$emit('toggle-reminder', task.id)">  
    <h3>
      {{ task.text }} 
      <i @click="$emit('delete-this-task', task.id)" class='fas fa-times'></i>  
    </h3>
    <p>
      {{ task.day }}
    </p>
  </div>
</template>

<script>
  export default {
    name: 'TaskComponent',
    props: {
      task: Object 
    },
  } 
</script>

<style scoped>
  .fas {
    color: red;
  }

  .task {
    background: #f4f4f4;
    margin: px;
    padding: 10px 20px;
    cursor: pointer;
  }

  .reminderrr {
    border-left: 5px solid green;
  }

  .task h3{
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
</style>

