<script setup>
import { RouterLink, useRoute } from "vue-router";
import Container from "./Container.vue";
import logo from "@/assets/logo.svg";

const route = useRoute();

const isActiveRoute = (path) => {
  return route.path === path;
};
</script>

<template>
  <header class="bg-green-700 h-14 flex">
    <Container>
      <div class="flex justify-between items-center h-full px-2">
        <RouterLink to="/" class="flex items-center gap-1">
          <span
            class="w-8 h-8 rounded-full bg-white flex justify-center items-center">
            <img :src="logo" alt="Vue logo" class="w-4 h-4" />
          </span>
          <span class="text-white font-medium text-sm">Vue Jobs</span>
        </RouterLink>
        <nav class="flex gap-1 md:gap-4 text-white text-sm">
          <RouterLink
            :class="
              isActiveRoute('/')
                ? 'bg-black px-3 py-1 rounded  bg-opacity-40 '
                : 'px-3 py-1 rounded hover:bg-black hover:bg-opacity-20 delay-100'
            "
            to="/"
            >Home</RouterLink
          >
          <RouterLink
            :class="
              isActiveRoute('/jobs')
                ? 'bg-black px-3 py-1 rounded  bg-opacity-40 '
                : 'px-3 py-1 rounded hover:bg-black hover:bg-opacity-20 delay-100'
            "
            to="/jobs"
            >Jobs</RouterLink
          >
          <!-- <RouterLink
            :class="
              isActiveRoute('/jobs/add-job')
                ? 'bg-black px-3 py-1 rounded  bg-opacity-40 '
                : 'px-3 py-1 rounded hover:bg-black hover:bg-opacity-20 delay-100'
            "
            to="/jobs/add-job"
            >Add Jobs</RouterLink
          > -->
        </nav>
      </div>
    </Container>
  </header>
</template>
