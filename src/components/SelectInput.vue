<template>
   <div>
    <label>{{label}}</label>
    <select :multiple="multi">
      <option v-for="option in options"
              :key="option"
              :value="value"
              @input="$emit('input', $event.target.value)">
             {{option}}
      </option>
    </select>
  </div>
</template>

<script>    
export default {
     name: 'SelectList',
     props: ['multi', 'options', 'name', 'label', 'value']
}
</script>

<style>

</style>