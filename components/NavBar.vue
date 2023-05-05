<template>
    <nav class="bg-purple-600 text-white shadow-lg text-lg flex justify-between p-3">
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="/about">About</NuxtLink>
        <NuxtLink to="/iphone">iPhones</NuxtLink>
        <NuxtLink to="/profile">Profile</NuxtLink>
        <p>Cart ({{cart.length}})</p>
    </nav>
</template>
<script setup>
 const cart = useCart();
</script>