<script setup>
import { ref } from "vue";
import BaseTree from "./BaseTree.vue";

const emit = defineEmits(["checkbox-data"]);
const searchQuery = ref("");
const selectedItems = ref([]);

const alldata = [
  {
    id: 1,
    title: "Food drinks",
    items: ["Beaches", "Parks", "Oceanarium", "Sanctuaries"],
  },
  {
    id: 2,
    title: "Nature",
    items: ["Underground places", "Gardens", "Reserves", "Gardens", "Volcanos", "Mountains", "Lakes"],
  },
];

const handleCheckboxStates = (items, id) => {
  const category = alldata.find((item) => item.id == id);
  selectedItems.value = selectedItems.value.filter(item => !category.items.includes(item));
  items.forEach((item, index) => {
    if (item) {
      selectedItems.value.push(category.items[index]);
    }
  });
  emit("checkbox-data", selectedItems.value);
};

</script>

<template>
  <div class="p-4">
    <div class="flex relative mb-8">
      <input type="text" v-model="searchQuery" class="px-8 py-2 w-full max-w-max border rounded-xl outline-none"
        placeholder="Type to choose" />
      <img src="/Vector.png" alt="search" class="absolute top-1/3 right-12" />
    </div>
    <div>
      <BaseTree v-for="(data, index) in alldata" :key="index" @checkbox-states="handleCheckboxStates" :data="data"
        :search-query="searchQuery" />
    </div>
  </div>
</template>

<style scoped></style>
