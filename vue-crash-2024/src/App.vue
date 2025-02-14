
<script>
export default {
  name: 'App',
  data() {
    return {
      name: 'Erick Alexabder Barrera Ochoa',
      status: 'pending',
      tasks:['task 1', 'task 2', 'task 3'],
      link: 'https://www.google.com'
    };
  },
  methods: {
    toogleStatus() {
      if (this.status === 'active'){
        this.status = 'pending'
      } else if (this.status === 'pending'){
        this.status = 'inactive'
      }else  {
        this.status = 'active'
      }
    }
  }
}
</script>


<template>
  <H1>{{ name }}</H1>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User in active</p>



  <h3>Tasks:</h3>
  <ul>
   <li v-for="task in tasks" :key="task">{{ task }} </li>

    
  </ul>
  <a :href="link">click Google</a>


  <button v-on:click="toogleStatus">Change status</button>
</template>




