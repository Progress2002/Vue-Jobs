<script setup>
import HeroSection from '@/components/HeroSection.vue';
import HomeCards from '@/components/HomeCards.vue';
import JobListings from '@/components/JobListings.vue';
</script>

<template>
  <main>
    <HeroSection />
    <HomeCards />
    <JobListings :limit="3" showButton="true"/>
  </main>
</template>
