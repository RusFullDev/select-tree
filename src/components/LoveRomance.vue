<script setup>
import { ref, computed, defineProps } from "vue";

const props = defineProps({
  data7: Array,
  searchQuery: String
});


const emit = defineEmits(['checkbox-states']);
const isOpen = ref(false);
const showRomance = () => {
  isOpen.value = !isOpen.value;
};

const checkboxs = ref(Array.from({ length: props.data7.length }, () => false));
const isCheck = computed({
  get() {
    return checkboxs.value.every((item) => item);
  },
  set(value) {
    checkboxs.value = Array.from({ length: props.data7.length }, () => value);
  },
});

const handleChange = () => {
  emit("chackbox-states", checkboxs.value)

};
const filteredData = computed(() => {
  if (!props.searchQuery) return props.data7;
  return props.data7.filter(item => item.toLowerCase().includes(props.searchQuery.toLowerCase()));
});

</script>

<template>
  <div class="header">
    <div class="flex gap-2 items-center mb-3">
      <input type="checkbox" v-model="isCheck" />
      <div class="flex gap-1 cursor-pointer" @click="showRomance">
        <p class="font-medium text-sm">Love & Romance</p>
        <img src="/Frame.png" alt="frame" class="text-2xl duration-200" :class="isOpen ? 'rotate-180' : ''" />
      </div>
    </div>
  </div>
  <div class="body overflow-hidden duration-200 px-5" :class="isOpen ? 'max-h-[500px]' : 'max-h-0'">
    <div class="flex gap-2 items-center mb-2" v-for="(item, index) in filteredData" :key="index">
      <input type="checkbox" v-model="checkboxs[index]" @change="handleChange" />
      <p class="font-medium text-sm">{{ item }}</p>
    </div>
  </div>
</template>

<style scoped></style>
