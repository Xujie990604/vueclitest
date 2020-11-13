<template>
    <div class="test">
        {{counter}}
        <button @click="counter++">+</button>
        <button @click="counter--">-</button>
    </div>
</template>

<script>
export default {
    name: 'Test',
    data() {
        return {
            counter: 0
        }
    },
    watch: {
        counter(newCounter, oldCounter) {
           
        }
    },
    created() {
        
    },
    methods: {
        
    }
}
</script>

<style scoped>

</style>