<script setup>
import { RouterLink, RouterView } from 'vue-router'
import myHeader from './views/partials/Navbar.vue'
import myFooter from './views/partials/Footer.vue'
</script>

<template>
    <myHeader></myHeader>
    <RouterView :key="$route.fullPath"/>
    <myFooter></myFooter>
</template>

