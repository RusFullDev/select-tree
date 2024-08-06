<script setup>
import { ref } from 'vue';
import Sidebar from '../src/components/Sidebar.vue';

const selectedData = ref([]);

const handleCheckboxData = (data) => {
  selectedData.value = data;
};

</script>

<template>
  <div class="flex h-screen p-5">
    <div class="w-[316px] fixed left-3 top-3 bottom-0 h-screen scroll-my-3 overflow-y-auto">
      <Sidebar @checkbox-data="handleCheckboxData" />
    </div>
    <div class="w-full ml-[316px] border h-[1000px] bg-[#F9F9F9]">
      <ul class="px-11 py-9 flex flex-wrap gap-4">
        <li v-for="item in selectedData" :key="item"
          class="flex gap-2 border bg-white border-gray-400 rounded-full text-center w-auto px-4 py-2">
          {{ item }}
          <p>X</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<style scoped></style>
