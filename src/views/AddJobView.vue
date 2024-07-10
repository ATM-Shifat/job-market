<script setup>

import router from '@/router';
import {reactive} from 'vue';
import axios from 'axios';
import {useToast} from 'vue-toastification';
import JobOption from '@/components/JobOption.vue';

import form from '@/components/JobOption.vue';


const toast = useToast();



// const form = reactive({
//     type: "Full-Time",
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

// const handleSubmit = async () =>{
//     const newJob = {
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
//         const response = await axios.post('/api/jobs', newJob);
//         toast.success('Job added successfully!');
//         router.push(`/jobs/${response.data.id}`);  
//     }catch(e){
//         console.error('New job addition failed', e);
//         toast.error('Failed to add job. Please try again later.');
//     }
// }

</script>

<template>
  <JobOption title="Add Job" button="Add Job"/>
</template>