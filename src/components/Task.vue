<template>
    <div  
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task']"
    >
         <h3>
            {{ task.text }}
            <i @click="$emit('delete-task', task.id)" class="fa-regular fa-circle-xmark" style="float: right" ></i>
        </h3>
         <p>{{ task.day }}</p>
    </div>
   
</template>

<script>
    export default {
        name: 'Task',
        props: {
            task: Object,
        },
}
</script>

<style scoped>
.fa-regular{
    color: rgb(255, 0, 0);
    align-items: right;
}
.task {
  padding: 10px;
  border-radius: 5px;
  margin-bottom: 10px;
  background-color: #6e6e6e;
}
.task-day {
  font-size: 14px;
  color: gray;
}

.task.reminder {
  border-left:5px solid green;
}
</style>
