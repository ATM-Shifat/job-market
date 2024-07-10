<script setup>

import {reactive, defineProps, onMounted} from 'vue';
import axios from 'axios';
import {useRoute, useRouter} from 'vue-router';
import {useToast} from 'vue-toastification';
import JobOption from '@/components/JobOption.vue';

// const route = useRoute();
// const router = useRouter();
// const toast = useToast();
// const jobId = route.params.id;


// const form = reactive({
//     type: "",
//     title:'',
//     description: '',
//     salary:'',
//     location:'',
//     company: {
//         name: '',
//         description: '',
//         contactEmail: '',
//         contactPhone: '',
//     }
// });

// const state = reactive({
//     job: Object,
//     isLoading: true,
// })



// const handleEdit = async () =>{
//     const updatedJob = {
//         type: form.type,
//         title: form.title,
//         description: form.description,
//         salary: form.salary,
//         location:form.location,
//         company: {
//             name: form.company.name,
//             description: form.company.description,
//             contactEmail: form.company.contactEmail,
//             contactPhone: form.company.contactPhone,
//         }
//     }

//     try{
//         const response = await axios.put(`/api/jobs/${jobId}`, updatedJob);
//         toast.success('Job updated successfully!');
//         router.push(`/jobs/${response.data.id}`);       
//     }catch(e){
//         console.error('Job info update failed', e);
//         toast.error('Failed to update job. Please try again later.');
//     }
// }

// onMounted( async()=> {
//     try{
//         const response = await axios.get(`/api/jobs/${jobId}`);
//         state.job = response.data;
        

//         form.type = state.job.type;
//         form.title = state.job.title;
//         form.description = state.job.description;
//         form.salary = state.job.salary;
//         form.location = state.job.location;
//         form.company.name = state.job.company.name;
//         form.company.description = state.job.company.description;
//         form.company.contactEmail = state.job.company.contactEmail;
//         form.company.contactPhone = state.job.company.contactPhone;

//     }catch(e){
//         console.error("Failed to fetch job info");
//     }finally{
//         state.isLoading = false;
//     }
// })

</script>


<template>
  <JobOption title="Edit Job" button="Change"/>
</template>