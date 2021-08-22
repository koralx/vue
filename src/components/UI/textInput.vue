<template>
  <input :value="modelValue" @input="updateInput" type="text">
</template>

<script>
export default {
  name: 'text-input',
  props: {
    modelValue: [String]
  },
  methods: {
   updateInput(event) {
     this.$emit('update:modelValue', event.target.value)
   }
  }
}
</script>

<style scoped>
input[type=text] {
  width: 50%;
  border: 0px black solid;
  border-bottom: 1px black solid;
  margin-bottom: 5px;
  outline: none;
  padding: 5px 5px 5px 0;
  font-size: 16px;
}
</style>