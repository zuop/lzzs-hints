<template>
  <div v-if="hints.length > 0" class="jz-hints">
    <div class="jz-flex jz-row jz-align-items-center title">
      <el-icon><WarningFilled /></el-icon> <span>{{ title }}</span>
    </div>
    <ul>
      <li v-for="(item, index) in hints" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>

<script setup>
import { WarningFilled } from "@element-plus/icons-vue";

defineProps({
  title: { type: String, default: "操作提示" },
  hints: { type: Array, default: () => [] }
});
</script>

<style lang="scss" scoped>
// 提示信息
.jz-hints {
  margin-top: 5px;
  margin-bottom: 5px;
  padding: 10px;
  background: rgba($color: $theme, $alpha: 0.1);

  .title {
    line-height: 28px;
    font-size: 14px;
    font-weight: 700;
    color: $theme;

    .el-icon {
      margin-right: 5px;
    }
  }

  ul {
    list-style-type: disc;
    padding-left: 20px;
    margin-top: 5px;
    margin-bottom: 0px;

    li {
      line-height: 28px;
      font-size: 14px;
      color: #748a8f;
    }
  }
}
</style>
