<template>
  <div id="app">
   
    <component v-for="(field, index) in schema"
        :key="index"
        :is="field.fieldType"
        :value="formData[field.name]"
        @input="updateForm(field.name, $event)"
        v-bind="field">
    </component>

  </div>
</template>
<script>

import TextInput from './TextInput'
import SelectList from './SelectInput'
import NumberInput from './NumberInput'

export default {
    name:'FormGenerator',
    props:['schema','value'],

  components:{
      TextInput, SelectList, NumberInput
  },
 data() {
   return {
       formData: this.value || {}
   }
 },
 methods: {
     updateForm(fieldName, value) {
         this.$set(this.formData, fieldName, value)
         this.$emit('input', this.formData)
     }
 }
}
</script>

