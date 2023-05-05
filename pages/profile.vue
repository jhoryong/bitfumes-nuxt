<template>
    <p>Welcome Horyong!</p>
</template>
<script setup>
    definePageMeta({
        layout: 'sidebar',
        middleware: () => {
            console.log('middleware!!')
        }
    })
</script>