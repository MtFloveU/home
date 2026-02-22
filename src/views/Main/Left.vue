<template>
  <!-- 当在移动端（宽度 < 721）且 Box 盒子被打开时，自动隐藏左侧组件，为盒子腾出空间 -->
  <div :class="(store.mobileOpenState || (store.boxOpenState && store.getInnerWidth < 721)) ? 'left hidden' : 'left'">
    <Message />
    <SocialLinks />
  </div>
</template>

<script setup>
import { mainStore } from "@/store";
import Message from "@/components/Message.vue";
import SocialLinks from "@/components/SocialLinks.vue";
const store = mainStore();
</script>

<style lang="scss" scoped>
.left {
  // flex: 1 0 0%;
  width: 50%;
  margin-right: 10px;
  transform: translateY(20px);
  &.hidden {
    display: none;
  }
  @media (max-width: 720px) {
    margin-right: 0;
    width: 100%;
  }
}
</style>