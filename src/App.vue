<script setup>
import { RouterView } from 'vue-router';
import Header from './components/Navbar.vue';
</script>

<template>
  <Header/>
  <div class="w-full h-[1px] bg-gray-400" />
  <RouterView />
</template>

