<!-- eslint-disable vue/no-parsing-error -->
<template>
  <div class="buttons">
    <p>排序</p>
    <button
      v-for="(button, index) in buttonsList"
      :key="index"
      type="button"
      class="btn"
      @click="changeOrderHandler(button)"
    >
      {{ button }}
    </button>
  </div>
  <div><JobsList :jobs="jobs" :order="activeOrder" /></div>
</template>

<script setup lang="ts">
import { reactive, ref } from 'vue';
import Job from '@/type/job';
import OrderTeam from '@/type/order';

import JobsList from '@/components/JobsList.vue';

const jobs = reactive<Job[]>([
  {
    title: '工程師',
    location: '台北',
    salary: 60000,
    id: '01',
  },
  {
    title: '木工',
    location: '台中',
    salary: 55000,
    id: '02',
  },
  {
    title: '室內設計師',
    location: '高雄',
    salary: 50000,
    id: '03',
  },
]);

const buttonsList: OrderTeam[] = ['名稱', '地點', '薪水'];
const activeOrder = ref<OrderTeam>(buttonsList[0]);

const changeOrderHandler = (order: OrderTeam) => {
  activeOrder.value = order;
};
</script>

<style scoped>
.buttons {
  display: flex;
  gap: 16px;
  justify-content: center;
  align-items: center;
}
.btn {
  outline: none;
  border: none;
  cursor: pointer;
  font-size: 20px;
  border-radius: 16px;
  padding: 8px 12px;
  background-color: white;
  color: gray;
}
.btn:hover {
  opacity: 0.6;
}
.btn:active {
  position: relative;
  top: 2px;
  left: 2px;
}
</style>
