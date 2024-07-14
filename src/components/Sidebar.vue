<script setup>
import { ref } from "vue";
import Nature from "./Nature.vue";
import FoodDrink from "./FoodDrink.vue";
import Culture from "./Culture.vue";
import AuthenticExperience from "./AuthenticExperience.vue";
import HealthBeauty from "./HealthBeauty.vue";
import FamilyKids from "./FamilyKids.vue";
import MusicDanceCinema from "./MusicDanceCinema.vue";
import LoveRomance from "./LoveRomance.vue";

const emit = defineEmits(['checkbox-data']);
const searchQuery = ref("");
const message = ref('');
const data = [
  "Beaches",
  "Parks",
  " Oceanarium",
  " Sanctuaries",
  "Underground places",
  "Gardens",
  "reserves",
  "Gardens",
  "Volcanos",
  "Mountains",
  "Lakes",
];
const data2 = [
  "Beaches",
  "Parks",
  " Oceanarium",
  " Sanctuaries",
  "Underground places",
  "Gardens",
  "reserves",
  "Gardens",
  "Volcanos",
  "Mountains",
  "Lakes",
];
const data3 = [
  "Beaches",
  "Parks",
  " Oceanarium",
  " Sanctuaries",
  "Underground places",
  "Gardens",
  "reserves",
  "Gardens",
  "Volcanos",
  "Mountains",
  "Lakes",
];
const data4 = [
  "Beaches",
  "Parks",
  " Oceanarium",
  " Sanctuaries",
  "Underground places",
  "Gardens",
  "reserves",
  "Gardens",
  "Volcanos",
  "Mountains",
  "Lakes",
];
const data5 = [
  "Beaches",
  "Parks",
  " Oceanarium",
  " Sanctuaries",
  "Underground places",
  "Gardens",
  "reserves",
  "Gardens",
  "Volcanos",
  "Mountains",
  "Lakes",
];
const data6 = [
  "Beaches",
  "Parks",
  " Oceanarium",
  " Sanctuaries",
  "Underground places",
  "Gardens",
  "reserves",
  "Gardens",
  "Volcanos",
  "Mountains",
  "Lakes",
];
const data7 = [
  "Beaches",
  "Parks",
  " Oceanarium",
  " Sanctuaries",
  "Underground places",
  "Gardens",
  "reserves",
  "Gardens",
  "Volcanos",
  "Mountains",
  "Lakes",
];
const data8 = [
  "Beaches",
  "Parks",
  " Oceanarium",
  " Sanctuaries",
  "Underground places",
  "Gardens",
  "reserves",
  "Gardens",
  "Volcanos",
  "Mountains",
  "Lakes",
];

const handleCheckboxStates = (states) => {
  message.value = states;
  let selectedItems = states.map((checked, index) => checked ? data[index] : null).filter(item => item !== null)
  emit('checkbox-data', selectedItems);
}


</script>

<template>
  <div class="p-4">
    <div class="flex relative mb-8">
      <input type="text" v-model="searchQuery" class="px-8 py-2 w-full max-w-max border rounded-xl outline-none"
        placeholder="Type to choose" />
      <img src="/Vector.png" alt="search" class="absolute top-1/3 right-12" />
    </div>
    <div>
      <FoodDrink @chackbox-states="handleCheckboxStates" :data='data' :search-query="searchQuery" />
      <Nature @chackbox-states="handleCheckboxStates" :data2='data2' :search-query="searchQuery" />
      <Culture @chackbox-states="handleCheckboxStates" :data3='data3' :search-query="searchQuery" />
      <HealthBeauty @chackbox-states="handleCheckboxStates" :data4='data4' :search-query="searchQuery" />
      <FamilyKids @chackbox-states="handleCheckboxStates" :data5='data5' :search-query="searchQuery" />
      <MusicDanceCinema @chackbox-states="handleCheckboxStates" :data6='data6' :search-query="searchQuery" />
      <LoveRomance @chackbox-states="handleCheckboxStates" :data7='data7' :search-query="searchQuery" />
      <AuthenticExperience @chackbox-states="handleCheckboxStates" :data8='data8' :search-query="searchQuery" />

    </div>
  </div>
</template>

<style scoped></style>
