<template>
    <div>
	    <label>{{label}}</label>
	    <input type="number"
         :value="value"
         @input="$emit('input', $event.target.value)"
         :name="name"
          placeholder="placeholder"
          :min="minValue">
    </div>
</template>

<script>
export default {
    name: 'NumberInput',
    props: ['placeholder', 'label', 'name','minValue','value']
}
</script>

<style>

</style>