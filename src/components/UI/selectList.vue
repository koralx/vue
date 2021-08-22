<template>
    <select v-model="modelValue" @change="changeOption">
        <option disabled value="">Выберите фильтр</option>
        <option 
        v-for="option in options" 
        :key="option.value" 
        :value="option.value">{{ option.name }}</option>
    </select>   
</template>

<script>
export default {
    name: 'select-list',
    props: {
        modelValue: {
            type: String
        },
        options: {
            type: Array,
            default: () => []
        }
    },
    methods: {
        changeOption(event) {
            this.$emit('update: modelValue', event.target.value)
        }
    }
}
</script>

<style scoped>
    select {
        width: 150px;
        height: 40px;
    }
</style>