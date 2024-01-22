<!--
 * @Autor: Lee
 * @Date: 2023-12-12 21:07:13
 * @LastEditTime: 2024-01-22 11:35:48
-->
<template>
  <van-tabbar v-model="active" :placeholder="true" :route="true" fixed>
    <van-tabbar-item
      v-for="(item, index) in tabbarData"
      :key="index"
      :icon="item.icon"
      :to="item.to"
    >
      {{ item.title }}
    </van-tabbar-item>
  </van-tabbar>
</template>

<script setup lang="ts">
import { ref, reactive } from "vue";

const active = ref(0);
const tabbarData = reactive([
  {
    icon: "wap-home-o",
    title: "主页",
    to: {
      name: "Home"
    }
  },
  {
    icon: "gem-o",
    title: "工具",
    to: {
      name: "Tools"
    }
  },
  {
    icon: "user-o",
    title: "应用",
    to: {
      name: "About"
    }
  }
]);
</script>
