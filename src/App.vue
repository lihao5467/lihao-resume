<script setup>
import { Flashlamp, TagOne, Workbench } from "@icon-park/vue-next";
import Module from "./components/Module.vue";
import Experience from "./components/Experience.vue";
import { reactive, ref } from "vue";
const personInfo = reactive([
  ["19112624873", "2315590235@qq.com"],
  ["22岁", "男"],
  ["专科", "软件技术"],
]);
const technologyStack = reactive([
  "熟练使用 HTML, CSS, JavaScript构建基础web应用。",
  "熟练掌握 Vue.js以及 VueRouter, Vuex, Pinia官方生态库。",
  "熟练使用 Element, AntDesign, Echarts常用组件库和图表库搭建应用页面。",
  "了解 Uniapp开发跨端应用程序,微信小程序开发。",
  "了解 Less, sass, Node.js, TypeScript的基本使用。",
  "了解 pnpm, npm常用包管理工具的使用以及 Webpack, Vite基本构建配置。",
]);
const HZWorkExperienceDescText = [
  "参与项目需求讨论, 完成前端技术选型。搭建项目前期工程化",
  "接入前端代码规范，快速完成项目开发",
];
const BRWorkExperienceDescText = [
  "维护公司已有项目, 开发项目新功能。快速完成上级分配的任务并且缩短项目交付周期。",
];
const HZOAProjectExperienceDescText = [
  "· 系统菜单权限管理, 使用递归匹配多级菜单，实现系统后台管理菜单新增删除排序。",
  "· 可视化配置表单, 使用VariantForm通过JSON数据格式完成用户自定义表单。",
  "· 接入Eslint, Prettier指定前端开发代码规范",
];
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
          title="重庆市荟至信息科技有限公司"
          location="重庆"
          start-date="2021-05"
          end-date="2022-02"
          :experience-desc-text="HZWorkExperienceDescText"
        ></Experience>
        <Experience
          class="mt-10"
          title="重庆市巴尔瑙尔科技有限公司"
          location="重庆"
          start-date="2020-08"
          end-date="2021-04"
          :experience-desc-text="BRWorkExperienceDescText"
        ></Experience>
      </Module>
      <Module class="work-experience" title="项目经验">
        <template #module-icon>
          <TagOne theme="filled" :size="24" />
        </template>
        <Experience
          title="荟至信息OA办公系统"
          :experience-desc-text="HZOAProjectExperienceDescText"
        ></Experience>
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
