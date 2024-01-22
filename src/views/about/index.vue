<!--
 * @Autor: Lee
 * @Date: 2023-12-12 21:07:13
 * @LastEditTime: 2024-01-22 15:14:19
-->
<script setup lang="ts" name="About">
import { reactive } from "vue";
const applicationList = reactive([
  {
    name: "ChatGPT",
    icon: "chatGPT",
    url: "http://www.wcysgxn.love"
  },
  {
    name: "测试-小1",
    icon: "test",
    url: "http://www.wcysgxn.love"
  },
  {
    name: "测试-小2",
    icon: "test",
    url: "http://www.wcysgxn.love"
  },
  {
    name: "测试-小3",
    icon: "test",
    url: "http://www.wcysgxn.love"
  },
  {
    name: "测试-小4",
    icon: "test",
    url: "http://www.wcysgxn.love"
  },
  {
    name: "测试-小5",
    icon: "test",
    url: "http://www.wcysgxn.love"
  }
]);
</script>
<template>
  <div class="application-root variiables-pd">
    <div class="text-center mt-[10px] font-semibold">应用集市</div>
    <div class="mt-[20px]">
      <!-- 设置垂直间距 -->
      <van-row :gutter="[20, 20]">
        <van-col v-for="(it, idx) in applicationList" :key="idx" span="12">
          <a
            class="flex flex-col items-center"
            href="http://www.wcysgxn.love"
            target="_blank"
          >
            <svg-icon class="text-[50px]" :name="it.icon" />
            <p class="text-[12px] mt-[10px]">{{ it.name }}</p>
          </a>
        </van-col>
      </van-row>
    </div>
  </div>
</template>
