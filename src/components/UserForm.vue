<template>
    <div>
       <h1>User Form</h1>
       <form @submit.prevent="submitForm">
         <div>
           <label for="name">Name:</label>
           <input type="text" id="name" v-model="form.name" required />
         </div>
         <div>
           <label for="email">Email:</label>
           <input type="email" id="email" v-model="form.email" required />
         </div>
         <div>
           <label for="age">Age:</label>
           <input type="number" id="age" v-model="form.age" required />
         </div>
         <button type="submit">Submit</button>
       </form>
    </div>
   </template>
   
   <script>
   export default {
    data() {
       return {
         form: {
           name: "",
           email: "",
           age: null,
         },
       };
    },
    methods: {
       submitForm() {
         this.$emit("add:user", this.form);
         this.form.name = "";
         this.form.email = "";
         this.form.age = null;
       },
    },
   };
   </script>