<template>
    <div>
        <button @click="increment">increment</button>
        <p>{{ count }}</p>
        <button @click="decrement">decrement</button>
    </div>
</template>

<script setup lang="ts">
const count = ref(0)
function increment() {
    count.value++
}
function decrement() {
    count.value--
}
</script>

<style scoped>

</style>