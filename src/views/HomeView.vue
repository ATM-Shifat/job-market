<script setup>
import Hero from '@/components/Hero.vue'
import HomeCards from '@/components/HomeCards.vue'
import JobListings from '@/components/JobListings.vue'
</script>

<template>
    <Hero />
    <HomeCards/>
    <!-- <HomeCards bg_color="bg-red-100"/> -->
    <JobListings :limit="3" :show-button="true" />
</template>