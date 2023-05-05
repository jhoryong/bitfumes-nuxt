<!-- 페이지는 반드시 하나의 root element 가 있어야 함. -->
<template>
    <div>
        <div>indeX!!    </div>
        <button @click="moveToAbout">Take me to about Page</button>
        <label>id</label>
        <input id="id" v-model="id" class="border-solid border-2 border-black">
        <label for="">password</label>
        <input id="pw" v-model="pw" class="border-solid border-2 border-black">
        <button @click="submit">submit</button>
        <p v-if="!isLoading">Your token is : {{token}}</p>
    </div>
</template>

<script setup lang="ts">

const id = ref('eve.holt@reqres.in');
const pw = ref('cityslicka');
const isLoading = ref(true)
const token = ref('')
async function submit() {
     const url = 'https://reqres.in/api/login'
     try {
         const {data, error} = await useFetch(url, {
            method: "post",
            body: {
                email: id,
                password: pw
            }
         })
         console.log(data.value, error.value?.data);
         if (error.value) {
            throw new Error(error.value.data.error)
         }
         token.value = data.value?.token;
         isLoading.value = false

        } catch(e) {
            console.error(e)
     }
}
function moveToAbout() {
    navigateTo('about   ')
}
</script>


<style lang="" scoped>

</style>