<template>
  <div id="app">
    <div id="nav">
      <h1>Welcome to vue form component 
      </h1>
       <form-generator :schema="schema" v-model="formData"></form-generator>
       <p>
      Hello {{formData.title}} {{formData.firstName}} {{formData.lastName}}, I hear you are {{formData.age}} years old.
    </p>
    </div>
  </div>
</template>
<script>
import FormGenerator from './components/FormGenerator'

export default {
  components:{
      FormGenerator
  },
 data() {
   return {
      formData: {
        firstName:'',
        age:'',
        lastName:'',
      },
      schema: [{
        fieldType: "SelectList",
        name: "title",
        multi: false,
        label: "Title",
        options: ["Ms", "Mr", "Mx", "Dr", "Madam", "Lord"]
      },
      {
        fieldType: "TextInput",
        placeholder: "First Name",
        label: "First Name",
        name: "firstName"
      },
      {
        fieldType: "TextInput",
        placeholder: "Last Name",
        label: "Last Name",
        name: "lastName"
      },
      {
        fieldType: "NumberInput",
        placeholder: "Age",
        name: "age",
        label: "Age",
        minValue: 0
      }
    ]
   }
 }
}
</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

div{
  padding:10px;
}

label{
  padding-right:10px;
}
</style>
