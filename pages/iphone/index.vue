<template>
    <div class="grid grid-cols-4 gap-4 mt-10">
        <NuxtLink to="/iphone/iphone-12" class="shadow-lg border rounded-lg">
            <h1>iPhone 12</h1>
            <div class="flex justify-center">
                <img class="w-40 bg-" src="/images/iphone-12.jpg">
            </div>
        </NuxtLink>
        <NuxtLink to="/iphone/iphone-12-pro" class="shadow-lg border rounded-lg">
            <h1>iPhone 12 pro</h1>
            <div class="flex justify-center">
                <img class="w-40 bg-" src="/images/iphone-12-pro.jpg">
            </div>
        </NuxtLink >
        <NuxtPage />
    </div>
</template>
<script setup>
useHead({
    title: "Nuxt3 - iphones"
})
</script>