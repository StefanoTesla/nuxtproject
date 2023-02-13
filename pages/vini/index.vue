<script setup>
const route = useRoute()
const {data: wines } = await useFetch('http://localhost:80/store-api/public/api/v1/wines')

</script>

<template>
    <section>
        <p>AAAAAAAAAA</p>
        <li v-for="wine in wines" v-bind:key="wine.name">
            <NuxtLink :to="route.path +'/'+ wine.slug">
            {{ wine.name }}
            </NuxtLink>
        </li>
    </section>

</template>


