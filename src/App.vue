<script setup lang="ts">
import { ref } from 'vue';

const isSidebarOpen = ref(true);

const toggleSidebar = () => {
  isSidebarOpen.value = !isSidebarOpen.value;
};

// 菜单配置数组
const menuItems: any = [
  {
    title: '首页',
    path: '/',
    svgPath: 'M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 0 001.414-1.414l-7-7z'
  },
  {
    title: '快速开始',
    path: '/start',
    svgPath: 'M13.5 5.5c0 .83.67 1.5 1.5 1.5h2a1.5 1.5 0 0 0 0-3h-2c-.83 0-1.5.67-1.5 1.5zm-7.5 5c0 .83.67 1.5 1.5 1.5h11a1.5 1.5 0 0 0 0-3h-11c-.83 0-1.5.67-1.5 1.5zm2 5c0 .83.67 1.5 1.5 1.5h8a1.5 1.5 0 0 0 0-3h-8c-.83 0-1.5.67-1.5 1.5z'
  },
  {
    title: '基础功能',
    path: '/test1',
    svgPath: 'M4 5a2 2 0 012-2h6a2 2 0 012 2v14l-5-2.5L4 19V5z M14 5a2 2 0 012-2h2a2 2 0 012 2v6a2 2 0 01-2 2h-2a2 2 0 01-2-2V5z M4 15a2 2 0 100 4 2 2 0 000-4z'
  },
  {
    title: '布局相关',
    path: '/test2',
    svgPath: 'M4 5a2 2 0 012-2h6a2 2 0 012 2v14l-5-2.5L4 19V5z M14 5a2 2 0 012-2h2a2 2 0 012 2v6a2 2 0 01-2 2h-2a2 2 0 01-2-2V5z M4 15a2 2 0 100 4 2 2 0 000-4z'
  },
  {
    title: '过渡相关',
    path: '/test3',
    svgPath: 'M4 5a2 2 0 012-2h6a2 2 0 012 2v14l-5-2.5L4 19V5z M14 5a2 2 0 012-2h2a2 2 0 012 2v6a2 2 0 01-2 2h-2a2 2 0 01-2-2V5z M4 15a2 2 0 100 4 2 2 0 000-4z'
  },
];
</script>

<template>
  <div class="flex h-screen bg-gradient-to-br from-indigo-50 to-blue-50 overflow-hidden">
    <!-- 左侧导航栏 -->
    <nav class="transition-all  duration-300 ease-in-out border-r border-gray-300"
      :class="isSidebarOpen ? 'w-50' : 'w-20'">
      <div class="h-full flex flex-col ">
        <!-- 导航栏头部 -->
        <div class="p-2 flex items-center justify-center border-b border-gray-300">
          <button v-if="isSidebarOpen" @click="toggleSidebar"
            class="rounded-full p-1.5 focus:outline-none cursor-pointer transition-all">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd"
                d="M15.707 4.293a1 1 0 010 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414l-5-5a1 1 0 010-1.414l5-5a1 1 0 011.414 0z"
                clip-rule="evenodd" />
            </svg>
          </button>
          <button v-else @click="toggleSidebar"
            class="w-full flex justify-center cursor-pointer rounded-full p-1.5 focus:outline-none transition-all">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd"
                d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z"
                clip-rule="evenodd" />
            </svg>
          </button>
        </div>

        <!-- 导航菜单 -->
        <div class="flex-1 overflow-y-auto py-6">
          <div class="space-y-1 px-3">
            <router-link v-for="item in menuItems" :key="item.path" :to="item.path" class="block" v-slot="{ isActive }">
              <div :class="[
                isActive ? 'bg-blue-500 text-white' : ' hover:bg-black/30 hover:text-white',
                isSidebarOpen ? 'px-4 py-3' : 'justify-center py-3',
                'flex items-center rounded-lg transition-all duration-200 mb-1'
              ]">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                  <path v-if="item.svgPath" :d="item.svgPath" />
                  <path v-if="item.svgPathRule" :fill-rule="item.svgPathRule.rule" :d="item.svgPathRule.d"
                    :clip-rule="item.svgPathRule.rule" />
                </svg>
                <span class="ml-3 font-medium" v-if="isSidebarOpen">{{ item.title }}</span>
              </div>
            </router-link>
          </div>
        </div>
      </div>
    </nav>

    <!-- 右侧内容区域 -->
    <main class="flex-1 flex flex-col overflow-y-auto">
      <router-view />
    </main>
  </div>
</template>

<style scoped></style>
