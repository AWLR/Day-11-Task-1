<template>
    <div>
       <h1>User List</h1>
       <table>
         <thead>
           <tr>
             <th>Name</th>
             <th>Email</th>
             <th>Age</th>
           </tr>
         </thead>
         <tbody>
           <tr v-for="user in users" :key="user.id">
             <td>{{ user.name }}</td>
             <td>{{ user.email }}</td>
             <td>{{ user.age }}</td>
           </tr>
         </tbody>
       </table>
    </div>
   </template>
   
   <script>
   export default {
    props: {
       users: {
         type: Array,
         required: true,
       },
    },
   };
   </script>