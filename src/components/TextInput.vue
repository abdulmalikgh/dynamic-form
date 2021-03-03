<template>
    <div>
	    <label>{{label}}</label>
	    <input type="text"
         :name="name"
          placeholder="placeholder"
          :value="value"
         @input="$emit('input', $event.target.value)">
    </div>
</template>

<script>
export default {
    name: 'TextInput',
    props: ['placeholder', 'label', 'name','value']
}
</script>

<style>

</style>