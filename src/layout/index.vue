<!--
 * @Autor: Lee
 * @Date: 2023-12-12 21:07:13
 * @LastEditTime: 2024-01-22 14:19:25
-->
<script setup lang="ts">
import tabbar from "@/components/Tabbar/index.vue";
import NavBar from "@/components/NavBar/index.vue";
import { useCachedViewStoreHook } from "@/store/modules/cachedView";
import { useDarkMode } from "@/hooks/useToggleDarkMode";
import { computed } from "vue";

const cachedViews = computed(() => {
  return useCachedViewStoreHook().cachedViewList;
});
console.log({ cachedViews });
</script>

<template>
  <div class="app-wrapper">
    <van-config-provider :theme="useDarkMode() ? 'dark' : 'light'">
      <nav-bar />
      <router-view v-slot="{ Component }">
        <keep-alive :include="cachedViews">
          <component :is="Component" />
        </keep-alive>
      </router-view>
      <tabbar />
    </van-config-provider>
  </div>
</template>

<style lang="less" scoped>
@import "@/styles/mixin.less";

.app-wrapper {
  .clearfix();
  position: relative;
  height: 100%;
  width: 100%;
}
</style>
