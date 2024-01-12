<template>
  <div id="app">
     <UserForm @add:user="addUser" />
     <UserList :users="users" />
  </div>
 </template>
 
 <script>
 import UserForm from "./components/UserForm.vue";
 import UserList from "./components/UserList.vue";
 
 export default {
  components: {
     UserForm,
     UserList,
  },
  data() {
     return {
       users: [],
       nextId: 1,
     };
  },
  methods: {
     addUser(user) {
       user.id = this.nextId++;
       this.users.push(user);
     },
  },
 };
 </script>