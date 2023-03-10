<script setup>
import { Flashlamp, TagOne, Workbench } from "@icon-park/vue-next";
import Module from "./components/Module.vue";
import Experience from "./components/Experience.vue";
import { reactive, ref } from "vue";
const personInfo = reactive([
  ["19112624873", "hao202417@gmail.com"],
  ["22岁", "男"],
  ["专科", "软件技术"],
]);
const technologyStack = reactive([
  "掌握前端流行框架, 具备Vue项目从0-1的开发和上线的实战经验。",
  "深入了解Vue底层原理及设计实现, 具备框架源码阅读能力。",
  "熟悉前端常用构建工具, 具备项目从0-1的项目工程化搭建能力。",
  "具备大屏可视化项目经验, 对常见大屏适配方案有过实际项目实践经验。",
  "具备小程序原生开发及uni-app跨端开发能力, 拥有实际项目经验。",
  "熟练使用常用组件库, 具备对ElementUI, AntDesignVue二次扩展封装能力。",
  "掌握git版本控制工具的使用, 熟悉常用命令, 具备多人协作开发能力。",
]);
const HZWorkExperienceDescText = [
  "参与项目需求讨论, 根据项目实际需求完成前端技术选型。",
  "搭建项目前期工程化, 接入前端代码规范, 高质量完成项目开发",
];
const BRWorkExperienceDescText = [
  "维护公司已有项目, 开发新功能。快速完成上级分配的任务并且缩短项目交付周期。",
];
// 项目 一
const HZOACoreTechnology =
  "主要技术栈: Vue2 + Element + Webpack + VariantForm + Less";
const HZOAProjectExperienceDescText = [
  "设计并实现系统菜单权限及按钮权限管理, 通过后端存储路由信息完成菜单可配置化。",
  "解决文件体积过大时上传缓慢, 采用文件切片极大的优化上传文件的速度。",
  "开发可视化配置表单, 使用VariantForm操作JSON数据完成用户自定义表单。",
  "增加系统单点登陆机制, 解决用户在多个系统之间跳转需要重复登陆的问题。",
  "封装常用的公共组件, 公共请求逻辑以及请求报错处理, 优化无意义的重复代码提高开发效率。",
  "优化前端代码和静态资源体积, 对JSBundle进行分包优化减少构建后的应用大小, 提高页面加载速度。",
];

// 项目 二
const HZAFZXCoreTechnology =
  "主要技术栈: Vue3 + Pinia + Vite + Echarts + Element-Plus + Sass";
const HZAFZXProjectExperienceDescText = [
  "从0-1搭建项目前期结构, 引入Eslint, Prettier指定前端开发基本规范。",
  "采用css scale作为大屏适配方案, 保证页面在同比例屏幕上的展示效果。",
  "封装Echarts外层容器组件, 减少图表初始化和图表重绘等重复代码。",
];

// 项目 三
const HZRepairCoreTechnology =
  "主要技术栈: Vue2 + Vuex + ElementUI + Webpack + Less";
const HZRepairProjectExperienceDescText = [
  "接入微信登陆处理登陆权限, 根据账号权限隐藏显示不同的tabbar页面以及对应的接口权限。",
  "封装上传图片请求, 对图片过大的情况利用Canvas进行图片裁剪保证详情页图片正常展示。",
  "对UniRequest api进行二次封装统一添加认证信息以及请求错误处理。",
];
</script>

<template>
  <div class="resume">
    <div class="top-bar"></div>
    <div class="person-info">
      <h1>李 豪</h1>
      <div class="info" v-for="item in personInfo" :key="item[0]">
        {{ item[0] }} | {{ item[1] }}
      </div>
    </div>
    <main>
      <Module class="technology-stack" title="个人优势">
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
          end-date="2023-03"
          :experience-desc-text="HZWorkExperienceDescText"
        ></Experience>
        <Experience
          class="mt-12"
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
          class="mt-12"
          title="安富中学大屏可视化看板"
          job-content="工作内容："
          :core-technology="HZAFZXCoreTechnology"
          :experience-desc-text="HZAFZXProjectExperienceDescText"
        ></Experience>
        <Experience
          class="mt-12"
          title="荟至信息综合云平台"
          job-content="工作内容："
          :core-technology="HZRepairCoreTechnology"
          :experience-desc-text="HZRepairProjectExperienceDescText"
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
