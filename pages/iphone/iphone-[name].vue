<template>
    <div>
        <Head>
            <Title>Nuxt3 - iPhone-{{name}}</Title>
        </Head>
        <p>iPhone {{name}}</p>
        <!-- <img :src="`/assets/images/iphone-${name}.jpg`"> -->
        <img class="w-40" :src="`/images/iphone-${name}.jpg`">
        <button v-if="!isInCart()" @click="addToCart" class="w-40 h-10 bg-purple-900 rounded text-white">Buy Now</button>
        <button v-else @click="addToCart" class="w-40 h-10 bg-purple-900 rounded text-white">Remove from Cart</button>
    </div>
</template>
<script setup>
const route = useRoute();

const name = computed(() => {
    console.log("name: ", route.params.name)
    return route.params.name;
})
const fullname = computed(() => {
    return 'iphone-' + name.value;
})

const cart = useCart();

function isInCart() {
    return Boolean(cart.value.find(e => e.name === fullname.value))
}

function addToCart() {
    const found = cart.value.find(e => e.name === fullname.value)
    if (found) {
        cart.value = cart.value.filter(e => e.name !== fullname.value)
    } else {
        cart.value.push({
            name: fullname.value
        })
    }
    console.log(cart.value)
}
// useHead({
//     title: `Nuxt3 - iphone-${route.params.name}`
// })
</script>