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
  "对前端css预处理语言 Less, sass有过实际开发使用。",
  "对Uniapp开发跨端应用程序,微信小程序开发有过了解与实践。",
  "熟悉pnpm, npm, yarn常用包管理工具的使用以及常见命令。",
  "了解前端工程化, 对Webpack, Vite前端构建工具有过项目输出。",
  "熟悉git版本控制工具的使用, 掌握常见命令和多人协作开发流程。",
]);
const HZWorkExperienceDescText = [
  "参与项目需求讨论, 完成前端技术选型。搭建项目前期工程化",
  "接入前端代码规范，快速完成项目开发",
];
const BRWorkExperienceDescText = [
  "维护公司已有项目, 开发新功能。快速完成上级分配的任务并且缩短项目交付周期。",
];
const HZOAProjectExperienceDescText = [
  "完成系统菜单权限管理, 实现多级菜单匹配, 使用递归代替循环匹配完成多级嵌套子路由的管理。",
  "解决文件体积过大时上传缓慢, 采用文件切片极大的优化上传文件的速度。",
  "开发可视化配置表单, 使用VariantForm操作JSON数据完成用户自定义表单。",
  "增加系统单点登陆机制, 解决用户在多个系统之间跳转需要重复登陆的问题。",
  "封装常用的公共组件, 公共请求逻辑以及请求报错处理, 优化无意义的重复代码提高开发效率。",
  "优化前端代码和静态资源体积, 对JSBundle进行分包优化减少构建后的应用大小, 提高页面加载速度。",
];
const HZOACoreTechnology =
  "主要技术栈: Vue2 + Element + Webpack + VariantForm + Less";

const HZAFZXProjectExperienceDescText = [
  "从0-1搭建项目前期结构, 引入Eslint, Prettier指定前端开发基本规范。",
  "采用css scale方案解决大屏适配。",
  "使用单点登陆机制, 让用户在多系统之间切换时无需重新登陆该系统。",
  "封装常用的公共组件, 公共请求逻辑以及请求报错处理, 优化无意义的重复代码提高开发效率。",
];
const HZAFZXCoreTechnology =
  "主要技术栈: Vue3 + Pinia + Vite + Echarts + Element-Plus + Sass";
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
        <Experience :experience-desc-text="technologyStack"></Experience>
      </Module>
      <Module class="work-experience" title="工作经历">
        <template #module-icon>
          <Workbench theme="filled" :size="24" />
        </template>
        <Experience
          title="重庆市荟至信息科技有限公司"
          location="重庆"
          start-date="2022-05"
          end-date="2023-02"
          :experience-desc-text="HZWorkExperienceDescText"
        ></Experience>
        <Experience
          class="mt-10"
          title="重庆市巴尔瑙尔科技有限公司"
          location="重庆"
          start-date="2021-08"
          end-date="2022-04"
          :experience-desc-text="BRWorkExperienceDescText"
        ></Experience>
      </Module>
      <Module class="project-experience" title="项目经验">
        <template #module-icon>
          <TagOne theme="filled" :size="24" />
        </template>
        <Experience
          title="荟至信息OA办公系统"
          job-content="工作内容："
          :core-technology="HZOACoreTechnology"
          :experience-desc-text="HZOAProjectExperienceDescText"
        ></Experience>
        <Experience
          class="mt-10"
          title="安富中学大屏可视化看板"
          job-content="工作内容："
          :core-technology="HZAFZXCoreTechnology"
          :experience-desc-text="HZAFZXProjectExperienceDescText"
        ></Experience>
      </Module>
    </main>
  </div>
</template>

<style lang="less">
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
