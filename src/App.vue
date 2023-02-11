<script setup>
import { Flashlamp, TagOne, Workbench } from "@icon-park/vue-next";
import Module from "./components/Module.vue";
import Experience from "./components/Experience.vue";
import { reactive, ref } from "vue";
const personInfo = reactive([
  ["19112624873", "2315590235@qq.com"],
  ["22岁", "男"],
  ["科科", "技术技术"],
]);
const technologyStack = reactive([
  "熟练掌握 HTML, CSS, JavaScript 和 TypeScript 等前端技术并在实际项目中投入使用。",
  "熟练掌握 HTML, CSS, JavaScript 和 TypeScript 等前端技术并在实际项目中投入使用。",
  "熟练掌握 HTML, CSS, JavaScript 和 TypeScript 等前端技术并在实际项目中投入使用。",
  "熟练掌握 HTML, CSS, JavaScript 和 TypeScript 等前端技术并在实际项目中投入使用。",
  "熟练掌握 HTML, CSS, JavaScript 和 TypeScript 等前端技术并在实际项目中投入使用。",
  "熟练掌握 HTML, CSS, JavaScript 和 TypeScript 等前端技术并在实际项目中投入使用。",
]);
</script>

<template>
  <div class="resume">
    <div class="top-bar"></div>
    <div class="person-info">
      <h1>李豪</h1>
      <div class="info" v-for="item in personInfo" :key="item[0]">
        {{ item[0] }} | {{ item[1] }}
      </div>
    </div>
    <main>
      <Module class="technology-stack" title="个人技术栈">
        <template #module-icon>
          <Flashlamp theme="filled" :size="24" />
        </template>
        <div
          class="stack"
          :class="{ 'mt-7': index !== 0 }"
          v-for="(item, index) in technologyStack"
          :key="item"
        >
          {{ item }}
        </div>
      </Module>
      <Module class="work-experience" title="工作经历">
        <template #module-icon>
          <Workbench theme="filled" :size="24" />
        </template>
        <Experience
          title="深圳市同行者科技有限公司"
          location="重庆"
          start-date="2021-10-01"
          end-date="2022-10-1"
        ></Experience>
      </Module>
      <Module class="work-experience" title="项目经历">
        <template #module-icon>
          <TagOne theme="filled" :size="24" />
        </template>
        <Experience title="深圳市同行者xxx应用"></Experience>
      </Module>
    </main>
  </div>
</template>

<style lang="less">
@import "@/assets/globalLessVarible.less";

.resume {
  width: 1024px;
  min-height: 1440px;
  margin: 0 auto;
  .top-bar {
    height: 16px;
    background-color: @dark-top-bar-color;
  }
  .person-info {
    display: flex;
    flex-direction: column;
    align-items: center;
    row-gap: 7px;
    margin-top: 25px;
    .info {
      color: @dark-color-01;
    }
  }
  main {
    padding: 0 40px;
    .technology-stack {
      .stack {
        color: @light-color-01;
      }
    }
  }
}
</style>
