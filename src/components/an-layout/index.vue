<!--
 * Desc: main 自动撑起页面剩余高度
 * File Created: Thursday, 5th November 2020 8:57:20 pm
-->

<template>
  <div class="an-layout">
    <header v-if="$scopedSlots.header">
      <!--
        @slot header 头部插槽内容
       -->
      <slot name="header"></slot>
    </header>
    <main class="an-layout-main" :style="`align-items: ${alignItems}`">
      <!-- @slot 默认插槽内容，中心main区域 -->
      <slot></slot>
    </main>
    <footer v-if="$scopedSlots.footer">
      <!-- @slot footer 脚部插槽内容 -->
      <slot name="footer"></slot>
    </footer>
  </div>
</template>

<script>
/**
 * 利用flex 自适应，main 插槽撑起剩余高度
 * @displayName an-layout
 */
export default {
  name: "an-layout",
  props: {
    /**
     * 中心main 区域的align-items属性配置
     */
    "align-items": {
      type: String,
      default: "self-start",
    },
  },
};
</script>

<style lang="scss" scoped>
.an-layout {
  height: 100%;
  display: flex;
  flex-direction: column;
  &-main {
    display: flex;
    flex: 1;
    flex-direction: column;
    // align-items: self-start; // TODO: 后来设置prop 控制
    align-items: center;
  }
}
</style>
