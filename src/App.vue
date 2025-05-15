<script setup>
import { RouterLink, RouterView } from "vue-router";

const paths = [
  { id: 1, name: "儀板表" },
  { id: 2, name: "看板管理" },
  {
    id: 3,
    label: "資料管理",
    children: [
      "人員管理",
      "車輛管理",
      "日誌管理",
      "出勤管理",
      "門禁管理",
      "派車管理",
      "費用管理",
    ],
  },
  { id: 4, name: "推送管理" },
  { id: 5, name: "權限管理" },
];
</script>

<template>
  <div class="d-flex">
    <div class="row container">
      <div
        class="col-2 bg-primary-subtle position-fixed top-0 bottom-0 mx-auto"
      >
        <img
          class="d-block w-75 mb-5"
          src="https://github.com/weijanlin/frontend/blob/main/microsys_logob290x6001.jpg?raw=true"
          alt="logo"
        />
        <div class="button-group">
          <p v-for="path in paths" :key="path.id">
            {{ path.name }}

            <!-- 子選單 -->
          <ul v-if="path.children" class="ml-6 mt-3 space-y-1">
            <li
              v-for="(child, cIdx) in path.children"
              :key="cIdx"
              class="flex justify-between items-center w-[148px] text-sm mb-4 text-blue-800 cursor-pointer hover:text-blue-600"
            >
              {{ child }}
            </li>
          </ul>
          </p>
        </div>
      </div>
      <div class="col-10"></div>
    </div>
  </div>

  <!-- <RouterView /> -->
</template>

<style scoped></style>
