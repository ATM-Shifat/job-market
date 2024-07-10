<script setup>

import {RouterLink} from 'vue-router';
import card from '@/components/Card.vue';
import { defineProps } from 'vue';

defineProps({
    bg_color:{
        type: String,
        default: 'bg-green-100',
    },
});

</script>


<template>
    <section class="py-4">
      <div class="container-xl lg:container m-auto">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 p-4 rounded-lg">
          
          <!-- <card bg="bg-green-100"> -->
          <card :bg="bg_color">

            <h2 class="text-2xl font-bold">For Developers</h2>
            <p class="mt-2 mb-4">
              Browse our Vue jobs and start your career today
            </p>
            <RouterLink to="/jobs"class="inline-block bg-black text-white rounded-lg px-4 py-2 hover:bg-gray-700">
              Browse Jobs
            </RouterLink>

          </card>

          <card :bg="bg_color">

            <h2 class="text-2xl font-bold">For Employers</h2>
            <p class="mt-2 mb-4">
              List your job to find the perfect developer for the role
            </p>
            <RouterLink to="/jobs/add"class="inline-block bg-green-600 text-white rounded-lg px-4 py-2 hover:bg-green-700">
              Add Job
            </RouterLink>

          </card>

        </div>
      </div>
    </section>
</template>