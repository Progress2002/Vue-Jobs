<script setup>
import { RouterLink } from "vue-router";
import Container from "./Container.vue";
</script>

<template>
  <Container>
    <div class="my-10 flex flex-col md:flex-row gap-3 justify-center">
      <div class="rounded-lg bg-gray-100 p-6 w-full shadow-md">
        <h2 class="font-bold text-2xl">For Developers</h2>
        <p class="mt-2 mb-4">
          Browse our Vue jobs and start your career today!
        </p>
        <RouterLink
          to="/jobs"
          type="button"
          class="inline-block text-white rounded-lg mt-2 text-sm bg-gray-950 hover:bg-gray-800 delay-100 px-4 py-2 active:scale-[.98]">
          Browse Jobs
        </RouterLink>
      </div>
      <div class="rounded-lg bg-green-100 w-full p-6 shadow-md">
        <h2 class="font-bold text-2xl">For Employers</h2>
        <p class="mt-2 mb-4">
          List your job to find the perfect developer for the role
        </p>
        <div
          class="inline-block  text-white rounded-lg mt-2 text-sm bg-gray-500 bg-opacity-30 hover:cursor-not-allowed delay-100 px-4 py-2">
          Add Job
        </div>
      </div>
    </div>
  </Container>
</template>
