<script setup>
import { RouterLink } from "vue-router";
import Container from "./Container.vue";
import JobListing from "./JobListing.vue";
import { defineProps, ref } from "vue";
import Jobs from "@/jobs.json";

defineProps({
  limit: Number,
  showButton: {
    type: Boolean,
    default: false,
  },
});

const jobs = ref([]);
const loading =  ref(true);

setTimeout(() => {
    jobs.value = Jobs;
    loading.value = false;
}, 1000);

</script>

<template>
  <section class="bg-blue-50 px-4 py-10">
    <Container>
      <h2 class="text-3xl font-bold text-green-500 mb-6 text-center">
        Browse Jobs
      </h2>
      <div v-if="loading" class="m-auto text-center font-semibold my-20">Loading...</div>
      <div v-else class="grid grid-cols-1 gap-6 md:grid-cols-2 lg:grid-cols-3">
        <JobListing
          v-for="job in jobs.slice(0, limit || jobs.length)"
          :key="job.id"
          :job="job" />
      </div>
      <section v-if="showButton && !loading" class="m-auto max-w-lg my-10 px-6">
        <RouterLink
          to="/jobs"
          class="block bg-black text-white text-center py-4 px-6 rounded-xl hover:bg-gray-700 active:scale-[.98]">
          View All Jobs
        </RouterLink>
      </section>
    </Container>
  </section>
</template>
