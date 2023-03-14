<template>
  <div><JobsList :jobs="jobs" /></div>
</template>

<script setup lang="ts">
import { reactive } from 'vue';
import Job from '@/type/job';

import JobsList from '@/components/JobsList.vue';

const jobs = reactive<Job[]>([
  {
    title: '工程師',
    location: '台灣',
    salary: 60000,
    id: '01',
  },
  {
    title: '木工',
    location: '台灣',
    salary: 55000,
    id: '02',
  },
  {
    title: '室內設計師',
    location: '台灣',
    salary: 50000,
    id: '03',
  },
]);
</script>

<style scoped></style>
