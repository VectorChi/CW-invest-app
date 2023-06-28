<script setup>
import { ref } from "vue";

const tabs = ref([
  { name: "Conservative", classid: "con" },
  { name: "Moderate", classid: "mod" },
  { name: "Aggressive", classid: "agg" },
]);

const activeTab = ref(0);
</script>

<template>
  <div class="tab">
    <div class="tab-pills">
      <div
        v-for="(tab, index) in tabs"
        :key="index"
        :class="['pill', tab.classid, { active: activeTab === index }]"
        @click="activeTab = index"
      >
        {{ tab.name }}
      </div>
    </div>
    <div class="filtered-result">
      <slot :name="tabs[activeTab].name"></slot>
    </div>
  </div>
</template>

<style scoped>
.tab-pills {
  display: flex;
  margin-top: 2rem;
  gap: 2rem;
}

.filtered-result {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  column-gap: 2rem;
  row-gap: 2rem;
}
.tab {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4rem;
}
</style>
