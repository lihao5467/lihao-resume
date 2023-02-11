<script setup>
import { Local, Time } from "@icon-park/vue-next";
import { reactive, ref } from "vue";
defineProps({
  title: {
    type: String,
    required: true,
  },
  location: {
    type: String,
  },
  startDate: {
    type: String,
  },
  endDate: {
    type: String,
  },
});
const experienceDescText = reactive([
  "参与需求讨论, 指定开发计划, 制定项目和开发规范, 参与需求讨论,",
  "参与需求讨论, 指定开发计划, 制定项目和开发规范",
  "参与需求讨论, 指定开发计划, 制定项目和开发规范",
]);
</script>

<template>
  <div class="experience">
    <div class="experience-top mb-10">
      <p class="title">{{ title }}</p>
      <div class="location" v-if="location">
        <Local />
        <span class="location-name ml-8">{{ location }}</span>
      </div>
    </div>
    <section class="experience-desc">
      <div class="experience-desc-text">
        <div
          class="text"
          :class="{ 'mt-7': index !== 0 }"
          v-for="(item, index) in experienceDescText"
          :key="item"
        >
          {{ item }}
        </div>
      </div>
      <div class="experience-desc-date" v-if="startDate && endDate">
        <Time />
        <span class="ml-8">{{ startDate }} - {{ endDate }}</span>
      </div>
    </section>
  </div>
</template>

<style scoped lang="less">
@import "@/assets/globalLessVarible.less";
.experience {
  .experience-top {
    display: flex;
    justify-content: space-between;
    .title {
      font-weight: 600;
      color: @dark-color-01;
    }
    .location {
      color: @light-color-01;
    }
  }
  .experience-desc {
    display: flex;
    justify-content: space-between;
    .experience-desc-text {
      padding-right: 116px;
      color: @dark-color-02;
    }
    .experience-desc-date {
      flex-shrink: 0;
      color: @light-color-01;
    }
  }
}
</style>
