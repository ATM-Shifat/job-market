<script setup>

//import jobInfo from '@/jobs.json';
import JobListing from '@/components/JobListing.vue';
import {ref, reactive, defineProps, onMounted} from 'vue';
import axios from 'axios';
import PulseLoader from 'vue-spinner/src/PulseLoader.vue';

//const jobs = ref([]);


defineProps({
    limit: Number,
    showButton: {
        type: Boolean,
        default: false,
    }
});

const state = reactive({
    jobs: [],
    isLoading: true,
});

onMounted(async () => {
    try{
       const response = await axios.get('http://localhost:5000/jobs');
       state.jobs = response.data;
    }catch(e){
        console.error("Error fetching info", e);
    }finally{
        state.isLoading = false;
    }
});

</script>

<template>
    <section class="bg-blue-50 px-4 py-10">
        <div class="container-xl lg:container m-auto">

            <h2 class="text-3xl font-bold text-green-500 mb-6 text-center">
                Browse Jobs
            </h2>

            <!-- Show Loader while isLoading is true -->

            <div v-if="state.isLoading === true" class="text-center tet-gray-500 py-6">
                <PulseLoader />
            </div>

            <!-- Show job listings while isLoading is false -->

            <div  v-else class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-2 gap-6 ">
                <!-- <div v-for="job in jobs.slice(0, limit || jobs.length)" :key="job">
                    {{ job.title }}
                </div> -->
                <JobListing v-for="job in state.jobs.slice(0, limit || state.jobs.length)" :key="job.id" :job="job"/>    
            </div>

        </div>   
    </section>

    <section v-if="showButton" class="m-auto max-w-lg my-10 px-6">

      <RouterLink to="/jobs" class="block bg-black text-white text-center py-4 px-6 rounded-xl hover:bg-gray-700">
        View All Jobs
      </RouterLink>
      
    </section>
    
</template>