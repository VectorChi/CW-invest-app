<script setup>
import axios from "axios";
import Tabs from "./Tabs.vue";
import { ref, onMounted, computed } from "vue";

const fundList = ref([]);

onMounted(async () => {
  try {
    const response = await axios.get(
      "https://dashboard.cowrywise.com/api/v2/funds/public/"
    );
    fundList.value = response.data.data;
    console.log(fundList.value);
  } catch (err) {
    console.log(err);
  }
});

const conservativeFunds = computed(() => {
  return fundList.value.filter((fund) => fund.risk === 1);
});
const moderateFunds = computed(() => {
  return fundList.value.filter((fund) => fund.risk === 2);
});
const aggressiveFunds = computed(() => {
  return fundList.value.filter((fund) => fund.risk === 3);
});
</script>

<template>
  <div class="fund-section-wrapper">
    <div class="fund-section">
      <div class="fund-head-container">
        <h3 class="fund-section-title">
          We offer a wide range of
          <span class="purple-accent">high yield </span> funds.
        </h3>
      </div>

      <div class="filter-pills">
        <Tabs>
          <template #Conservative>
            <div
              v-for="fund in conservativeFunds"
              :id="fund.id"
              class="fund-card"
            >
              <div class="card-content">
                <div class="f-img-name">
                  <img
                    src="../assets/images/conservative.png"
                    alt="f-img"
                    class="f-img"
                  />
                  <p class="f-name">{{ fund.name }}</p>
                </div>

                <div class="annual-return">
                  <p class="year">Return This Year</p>
                  <p class="return">
                    {{ Math.round(fund.returns * 10000) / 100 }}%
                  </p>
                </div>
              </div>

              <!-- cta -->
              <div>
                <slot></slot>
              </div>
            </div>
          </template>

          <template #Moderate>
            <div v-for="fund in moderateFunds" :id="fund.id" class="fund-card">
              <div class="card-content">
                <div class="f-img-name">
                  <img
                    src="../assets/images/moderate.png"
                    alt="f-img"
                    class="f-img"
                  />
                  <p class="f-name">{{ fund.name }}</p>
                </div>

                <div class="annual-return">
                  <p class="year">Return this year</p>
                  <p class="return">
                    {{ Math.round(fund.returns * 10000) / 100 }}%
                  </p>
                </div>
              </div>

              <!-- cta -->
              <div>
                <slot></slot>
              </div>
            </div>
          </template>

          <template #Aggressive>
            <div
              v-for="fund in aggressiveFunds"
              :id="fund.id"
              class="fund-card"
            >
              <div class="card-content">
                <div class="f-img-name">
                  <img
                    src="../assets/images/Aggressive.png"
                    alt="f-img"
                    class="f-img"
                  />
                  <p class="f-name">{{ fund.name }}</p>
                </div>

                <div class="annual-return">
                  <p class="year">Return this year</p>
                  <p class="return">
                    {{ Math.round(fund.returns * 10000) / 100 }}%
                  </p>
                </div>
              </div>

              <!-- cta -->
              <div>
                <slot></slot>
              </div>
            </div>
          </template>

          <!-- end of cards -->
        </Tabs>
      </div>

      <!-- end fo list -->
    </div>
  </div>
</template>

<style scoped>
.fund-section-wrapper {
  background-color: var(--color-lightpurple);
  margin-top: 8rem;
}

.fund-section,
.fund-head-container,
.filter-pills {
  display: flex;
}
.fund-section {
  flex-direction: column;
  width: 80%;
  margin: 0 auto;
  padding: 6rem 0;
  justify-content: center;
  align-items: center;
}
.fund-head-container {
  flex-direction: column;
  align-items: center;
  gap: 3rem;
  width: 42%;
}
.fund-section-title {
  font-size: 3rem;
  color: var(--color-black);
  text-align: center;
  font-weight: 700;
  line-height: 125%;
  letter-spacing: -2px;
}
.purple-accent {
  color: var(--color-purple);
  font-weight: 700;
}
.filter-pills {
  gap: 2rem;
}
</style>
