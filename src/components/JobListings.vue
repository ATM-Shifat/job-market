<script setup>
import jobInfo from '@/jobs.json';
import JobListing from '@/components/JobListing.vue';
import {ref, defineProps } from 'vue';

const jobs = ref(jobInfo);


defineProps({
    limit: Number,
    showButton: {
        type: Boolean,
        default: false,
    }
});

</script>

<template>
    <section class="bg-blue-50 px-4 py-10">
        <div class="container-xl lg:container m-auto">
            <h2 class="text-3xl font-bold text-green-500 mb-6 text-center">
                Browse Jobs
            </h2>
            <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-2 gap-6 ">
                <!-- <div v-for="job in jobs.slice(0, limit || jobs.length)" :key="job">
                    {{ job.title }}
                </div> -->
                
                <JobListing v-for="job in jobs.slice(0, limit || jobs.length)" :key="job.id" :job="job"/>

                    
            </div>
        </div>   
    </section>

    <section v-if="showButton" class="m-auto max-w-lg my-10 px-6">
      <a
        href="jobs.html"
        class="block bg-black text-white text-center py-4 px-6 rounded-xl hover:bg-gray-700"
        >View All Jobs</a
      >
    </section>
    
</template>