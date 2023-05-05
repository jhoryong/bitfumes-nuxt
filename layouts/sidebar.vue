<template>
    <main class="user-layout">
        <article class="sidebar">
            <p>dashboard</p>
            <p>settings</p>
        </article>
        <section>
            <slot></slot>
        </section>
    </main>
</template>

<script setup lang="ts">
    definePageMeta({
        layout: 'default'
    })
</script>
<style>
.sidebar {
    display: flex;
    flex-direction: column;
}
.user-layout {
    display: flex; 
}
</style>