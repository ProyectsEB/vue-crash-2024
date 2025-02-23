
<script setup>
import { ref } from 'vue';

 
    const name = ref('Erick Alexander Barrera Ochoa');
    const  status = ref('active');
    const  tasks = ref(['task 1', 'task 2', 'task 3']);
    const newTask = ref('');

    const toogleStatus = () => {
      if (status.value === 'active'){
        status.value = 'pending'
      } else if (status.value === 'pending'){
        status.value = 'inactive'
      }else  {
        status.value = 'active'
      }

    };

    
 
</script>


<template>
  <H1>{{ name }}</H1>
  <form @submit.prevent="addTask">
    <label for="newTask">Add Task</label>
    <input type="text" id="newTask" v-model="newTask">
  </form>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User in active</p>



  <h3>Tasks:</h3>
  <ul>
   <li v-for="task in tasks" :key="task">{{ task }} </li>

    
  </ul>


  <button v-on:click="toogleStatus">Change status</button>
</template>




