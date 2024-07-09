<script setup>

import NavBar from '@/components/NavBar.vue'
import { RouterView } from 'vue-router';


</script>

<template>
  <NavBar/>
  <RouterView/>
  <!-- <Hero />
  <HomeCards/>
  <HomeCards bg_color="bg-red-100"/> 
  <JobListings :limit="3" :show-button="false" /> -->
</template>
