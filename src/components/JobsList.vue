<template>
  <div class="job-list">
    <ul>
      <li v-for="job in props.jobs" :key="job.id">
        <h2>{{ job.title }} in {{ job.location }}</h2>
        <div class="salary">
          <p>
            {{ job.salary }}
          </p>
        </div>
        <div class="description">
          <p>
            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Dolores
            laboriosam perspiciatis eligendi accusantium ratione nam nulla quos.
            Quidem id assumenda obcaecati itaque ad asperiores, molestias
            officia, et cum ipsa nam.
          </p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script lang="ts" setup>
import { PropType } from 'vue';
import Job from '@/type/job';

const props = defineProps({
  jobs: {
    type: Array as PropType<Job[]>,
  },
});
</script>

<style scoped>
.job-list {
  max-width: 960px;
  margin: 40px auto;
}
.job-list ul {
  padding: 0;
}
.job-list li {
  list-style-type: none;
  background: white;
  padding: 16px;
  margin: 16px 0;
  border-radius: 4px;
}
.job-list h2 {
  margin: 0 0 10px;
  text-transform: capitalize;
}
.salary {
  display: flex;
}
.salary img {
  width: 30px;
}
.salary p {
  color: #17bf66;
  font-weight: bold;
  margin: 10px 4px;
}
</style>
