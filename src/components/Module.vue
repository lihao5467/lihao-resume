<script setup>
import { reactive, ref } from "vue";
defineProps({
  title: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div class="module">
    <div class="module-top">
      <slot name="module-icon"></slot>
      <span class="module-title">{{ title }}</span>
    </div>
    <div class="module-content">
      <slot></slot>
    </div>
  </div>
</template>

<style scoped lang="less">
.module {
  margin-top: 20px;
  .module-top {
    display: flex;
    align-items: center;
    column-gap: 10px;
    margin-bottom: 15px;
    padding-bottom: 5px;
    border-bottom: 2px solid @dark-top-bar-color;
    .icon {
      height: 24px;
    }
    .module-title {
      font-size: 20px;
      font-weight: 600;
      color: @dark-top-bar-color;
    }
  }
}
</style>
