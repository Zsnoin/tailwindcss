<template>
    <div class="container mx-auto py-8 px-4 max-w-6xl">
        <h1 class="text-3xl font-bold mb-8 text-center text-indigo-700">Tailwind CSS 4.0 响应式设计</h1>

        <!-- 响应式基础 -->
        <section class="mb-12 bg-white rounded-lg shadow-md p-6">
            <h2 class="text-2xl font-semibold mb-4 text-indigo-600 border-b pb-2">响应式设计基础</h2>

            <div class="space-y-6">
                <p class="text-gray-700">Tailwind CSS 提供了强大的响应式设计工具，使用简单的前缀可以为不同屏幕尺寸应用不同样式。</p>

                <!-- 响应式断点 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-3 text-indigo-500">1. 默认响应式断点</h3>
                    <p class="mb-4">Tailwind CSS 4.0 包含以下默认断点:</p>

                    <div class="overflow-x-auto">
                        <table class="min-w-full bg-white border border-gray-300">
                            <thead>
                                <tr>
                                    <th class="py-2 px-4 border-b border-gray-300 text-left">断点前缀</th>
                                    <th class="py-2 px-4 border-b border-gray-300 text-left">最小宽度</th>
                                    <th class="py-2 px-4 border-b border-gray-300 text-left">CSS</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td class="py-2 px-4 border-b border-gray-300"><code>sm</code></td>
                                    <td class="py-2 px-4 border-b border-gray-300">640px</td>
                                    <td class="py-2 px-4 border-b border-gray-300"><code>@media (min-width: 640px) { ... }</code></td>
                                </tr>
                                <tr>
                                    <td class="py-2 px-4 border-b border-gray-300"><code>md</code></td>
                                    <td class="py-2 px-4 border-b border-gray-300">768px</td>
                                    <td class="py-2 px-4 border-b border-gray-300"><code>@media (min-width: 768px) { ... }</code></td>
                                </tr>
                                <tr>
                                    <td class="py-2 px-4 border-b border-gray-300"><code>lg</code></td>
                                    <td class="py-2 px-4 border-b border-gray-300">1024px</td>
                                    <td class="py-2 px-4 border-b border-gray-300"><code>@media (min-width: 1024px) { ... }</code></td>
                                </tr>
                                <tr>
                                    <td class="py-2 px-4 border-b border-gray-300"><code>xl</code></td>
                                    <td class="py-2 px-4 border-b border-gray-300">1280px</td>
                                    <td class="py-2 px-4 border-b border-gray-300"><code>@media (min-width: 1280px) { ... }</code></td>
                                </tr>
                                <tr>
                                    <td class="py-2 px-4 border-b border-gray-300"><code>2xl</code></td>
                                    <td class="py-2 px-4 border-b border-gray-300">1536px</td>
                                    <td class="py-2 px-4 border-b border-gray-300"><code>@media (min-width: 1536px) { ... }</code></td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>

                <!-- 使用方法 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-3 text-indigo-500">2. 响应式前缀使用</h3>
                    <p class="mb-4">在类名前添加断点前缀（如 <code>md:</code>），只有在该断点及以上屏幕尺寸才会应用样式。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <h4 class="font-medium mb-2">响应式示例：</h4>
                            <div class="bg-blue-100 p-4 rounded">
                                <div class="bg-white p-4 rounded shadow-sm text-center font-medium
                                            text-red-500 sm:text-blue-500 md:text-green-500 
                                            lg:text-purple-500 xl:text-orange-500 2xl:text-teal-500">
                                    调整浏览器大小查看变化
                                </div>
                                <p class="mt-2 text-sm text-gray-600">
                                    默认: 红色 <br>
                                    sm (≥640px): 蓝色 <br>
                                    md (≥768px): 绿色 <br>
                                    lg (≥1024px): 紫色 <br>
                                    xl (≥1280px): 橙色 <br>
                                    2xl (≥1536px): 蓝绿色
                                </p>
                            </div>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">代码示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
&lt;div class="text-red-500 sm:text-blue-500 md:text-green-500 
            lg:text-purple-500 xl:text-orange-500 
            2xl:text-teal-500"&gt;
  调整浏览器大小查看变化
&lt;/div&gt;</pre>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 响应式布局 -->
        <section class="mb-12 bg-white rounded-lg shadow-md p-6">
            <h2 class="text-2xl font-semibold mb-4 text-indigo-600 border-b pb-2">响应式布局案例</h2>

            <div class="space-y-6">
                <!-- 响应式网格 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-3 text-indigo-500">1. 响应式网格布局</h3>
                    <p class="mb-4">使用 <code>grid-cols-{n}</code> 结合响应式前缀创建适应不同屏幕的网格布局。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div>
                            <h4 class="font-medium mb-2">效果示例：</h4>
                            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-6 gap-2">
                                <div v-for="i in 12" :key="i" 
                                    class="bg-indigo-500 h-12 rounded-md flex items-center justify-center text-white font-bold">
                                    {{ i }}
                                </div>
                            </div>
                            <p class="mt-2 text-sm text-gray-600">
                                默认: 1列 <br>
                                sm: 2列 <br>
                                md: 3列 <br>
                                lg: 4列 <br>
                                xl: 6列
                            </p>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">代码示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
&lt;div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 
            lg:grid-cols-4 xl:grid-cols-6 gap-2"&gt;
  &lt;div v-for="i in 12" :key="i" 
      class="bg-indigo-500 h-12 rounded-md flex 
             items-center justify-center text-white font-bold"&gt;
   <!-- {{ i }} -->
  &lt;/div&gt;
&lt;/div&gt;</pre>
                        </div>
                    </div>
                </div>

                <!-- 响应式 Flex 布局 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-3 text-indigo-500">2. 响应式 Flex 方向</h3>
                    <p class="mb-4">结合 <code>flex-{direction}</code> 和响应式前缀实现在不同屏幕上改变 flex 方向。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div>
                            <h4 class="font-medium mb-2">效果示例：</h4>
                            <div class="flex flex-col md:flex-row gap-2 bg-gray-100 p-2 rounded">
                                <div class="bg-blue-500 p-4 rounded text-white font-bold">项目 1</div>
                                <div class="bg-blue-500 p-4 rounded text-white font-bold">项目 2</div>
                                <div class="bg-blue-500 p-4 rounded text-white font-bold">项目 3</div>
                            </div>
                            <p class="mt-2 text-sm text-gray-600">
                                默认 (窄屏): 纵向排列 <br>
                                md 及以上: 横向排列
                            </p>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">代码示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
&lt;div class="flex flex-col md:flex-row gap-2"&gt;
  &lt;div class="bg-blue-500 p-4 rounded text-white font-bold"&gt;
    项目 1
  &lt;/div&gt;
  &lt;div class="bg-blue-500 p-4 rounded text-white font-bold"&gt;
    项目 2
  &lt;/div&gt;
  &lt;div class="bg-blue-500 p-4 rounded text-white font-bold"&gt;
    项目 3
  &lt;/div&gt;
&lt;/div&gt;</pre>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 高级响应式功能 -->
        <section class="mb-12 bg-white rounded-lg shadow-md p-6">
            <h2 class="text-2xl font-semibold mb-4 text-indigo-600 border-b pb-2">高级响应式功能</h2>

            <div class="space-y-6">
                <!-- 响应式显示和隐藏 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-3 text-indigo-500">1. 响应式显示/隐藏元素</h3>
                    <p class="mb-4">使用 <code>hidden</code> 和 <code>block</code> 等类结合响应式前缀控制元素可见性。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div>
                            <h4 class="font-medium mb-2">效果示例：</h4>
                            <div class="bg-gray-100 p-4 rounded">
                                <div class="hidden sm:block md:hidden lg:block bg-green-200 p-2 mb-2 rounded">
                                    在 sm 和 lg 以上显示，在 md 隐藏
                                </div>
                                <div class="block sm:hidden md:block lg:hidden bg-red-200 p-2 rounded">
                                    在默认和 md 显示，在 sm 和 lg 以上隐藏
                                </div>
                            </div>
                            <p class="mt-2 text-sm text-gray-600">
                                调整浏览器大小查看元素的显示和隐藏
                            </p>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">代码示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
&lt;div class="hidden sm:block md:hidden lg:block 
            bg-green-200 p-2 mb-2 rounded"&gt;
  在 sm 和 lg 以上显示，在 md 隐藏
&lt;/div&gt;

&lt;div class="block sm:hidden md:block lg:hidden 
            bg-red-200 p-2 rounded"&gt;
  在默认和 md 显示，在 sm 和 lg 以上隐藏
&lt;/div&gt;</pre>
                        </div>
                    </div>
                </div>

                <!-- 自定义响应式断点 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-3 text-indigo-500">2. 自定义响应式断点</h3>
                    <p class="mb-4">Tailwind CSS 4.0 允许在配置文件中定制自己的断点。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div>
                            <h4 class="font-medium mb-2">配置示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
// tailwind.config.js
module.exports = {
  theme: {
    screens: {
      'xs': '480px',
      'sm': '640px',
      'md': '768px',
      'lg': '1024px',
      'xl': '1280px',
      '2xl': '1536px',
      'tablet': '992px',
      'desktop': '1200px',
      'wide': '1440px',
    }
  }
}</pre>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">使用示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
&lt;div class="text-sm xs:text-base tablet:text-lg desktop:text-xl 
            wide:text-2xl"&gt;
  使用自定义断点调整文本大小
&lt;/div&gt;

&lt;div class="grid grid-cols-1 tablet:grid-cols-2 
            desktop:grid-cols-3 wide:grid-cols-4"&gt;
  使用自定义断点的网格布局
&lt;/div&gt;</pre>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 高级媒体查询 -->
        <section class="mb-12 bg-white rounded-lg shadow-md p-6">
            <h2 class="text-2xl font-semibold mb-4 text-indigo-600 border-b pb-2">高级媒体查询</h2>

            <div class="space-y-6">
                <!-- 暗黑模式 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-3 text-indigo-500">1. 暗黑模式响应</h3>
                    <p class="mb-4">使用 <code>dark:</code> 变体根据用户系统偏好应用暗黑模式样式。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div>
                            <h4 class="font-medium mb-2">效果示例：</h4>
                            <div class="p-4 bg-white dark:bg-gray-800 rounded-lg border border-gray-200 dark:border-gray-700">
                                <h5 class="text-gray-900 dark:text-white font-medium">支持暗黑模式的卡片</h5>
                                <p class="text-gray-700 dark:text-gray-300 mt-2">
                                    此元素根据系统偏好自动切换明暗模式。
                                </p>
                            </div>
                            <p class="mt-2 text-sm text-gray-600">
                                注意：需要在系统设置中切换暗黑模式查看效果
                            </p>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">代码示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
&lt;div class="p-4 bg-white dark:bg-gray-800 rounded-lg 
            border border-gray-200 dark:border-gray-700"&gt;
  &lt;h5 class="text-gray-900 dark:text-white font-medium"&gt;
    支持暗黑模式的卡片
  &lt;/h5&gt;
  &lt;p class="text-gray-700 dark:text-gray-300 mt-2"&gt;
    此元素根据系统偏好自动切换明暗模式。
  &lt;/p&gt;
&lt;/div&gt;</pre>
                            <p class="mt-2 text-sm">配置暗黑模式:</p>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto mt-2">
// tailwind.config.js
module.exports = {
  darkMode: 'media', // 使用操作系统偏好
  // 或者
  darkMode: 'class', // 使用类名手动控制
}</pre>
                        </div>
                    </div>
                </div>

                <!-- 方向响应 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-3 text-indigo-500">2. 方向响应设计</h3>
                    <p class="mb-4">使用 <code>portrait:</code> 和 <code>landscape:</code> 变体响应设备方向。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div>
                            <h4 class="font-medium mb-2">效果示例：</h4>
                            <div class="bg-gray-100 p-4 rounded">
                                <div class="bg-blue-200 portrait:bg-green-200 landscape:bg-purple-200 p-4 rounded">
                                    <p class="portrait:block landscape:hidden">当前是竖屏模式</p>
                                    <p class="portrait:hidden landscape:block">当前是横屏模式</p>
                                </div>
                            </div>
                            <p class="mt-2 text-sm text-gray-600">
                                旋转设备查看效果（在移动设备上更明显）
                            </p>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">代码示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
&lt;div class="bg-blue-200 portrait:bg-green-200 
            landscape:bg-purple-200 p-4 rounded"&gt;
  &lt;p class="portrait:block landscape:hidden"&gt;
    当前是竖屏模式
  &lt;/p&gt;
  &lt;p class="portrait:hidden landscape:block"&gt;
    当前是横屏模式
  &lt;/p&gt;
&lt;/div&gt;</pre>
                            <p class="mt-2 text-sm">配置方向变体:</p>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto mt-2">
// tailwind.config.js
module.exports = {
  plugins: [
    require('@tailwindcss/orientation')
  ]
}</pre>
                        </div>
                    </div>
                </div>

                <!-- 打印媒体查询 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-3 text-indigo-500">3. 打印媒体查询</h3>
                    <p class="mb-4">使用 <code>print:</code> 变体控制打印时的样式。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div>
                            <h4 class="font-medium mb-2">效果示例：</h4>
                            <div class="bg-blue-100 p-4 print:bg-white print:p-0 rounded print:rounded-none border border-blue-200 print:border-0">
                                <h5 class="text-xl font-bold print:text-black">打印优化标题</h5>
                                <p class="mt-2 print:text-black">这段文本在打印时会使用黑色，没有背景色。</p>
                                <button class="mt-4 bg-blue-500 text-white px-4 py-2 rounded print:hidden">
                                    打印时隐藏的按钮
                                </button>
                                <div class="hidden print:block mt-4 text-gray-800">
                                    仅在打印时显示的页脚信息
                                </div>
                            </div>
                            <p class="mt-2 text-sm text-gray-600">
                                尝试打印此页面（或使用打印预览）查看效果
                            </p>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">代码示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
&lt;div class="bg-blue-100 p-4 print:bg-white print:p-0 
            rounded print:rounded-none 
            border border-blue-200 print:border-0"&gt;
  &lt;h5 class="text-xl font-bold print:text-black"&gt;
    打印优化标题
  &lt;/h5&gt;
  &lt;p class="mt-2 print:text-black"&gt;
    这段文本在打印时会使用黑色，没有背景色。
  &lt;/p&gt;
  &lt;button class="mt-4 bg-blue-500 text-white px-4 py-2 
                 rounded print:hidden"&gt;
    打印时隐藏的按钮
  &lt;/button&gt;
  &lt;div class="hidden print:block mt-4 text-gray-800"&gt;
    仅在打印时显示的页脚信息
  &lt;/div&gt;
&lt;/div&gt;</pre>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 高级响应式模式 -->
        <section class="mb-12 bg-white rounded-lg shadow-md p-6">
            <h2 class="text-2xl font-semibold mb-4 text-indigo-600 border-b pb-2">响应式模式策略</h2>

            <div class="space-y-6">
                <!-- 移动优先设计 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-3 text-indigo-500">1. 移动优先设计</h3>
                    <p class="mb-4">Tailwind 采用移动优先设计模式，默认样式针对小屏幕，使用断点前缀为大屏幕设置样式。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div>
                            <h4 class="font-medium mb-2">良好实践示例：</h4>
                            <div class="bg-white p-4 rounded shadow-sm">
                                <div class="flex flex-col md:flex-row gap-4">
                                    <div class="w-full md:w-1/3 bg-gray-100 p-4 rounded">
                                        侧边栏（移动端为全宽）
                                    </div>
                                    <div class="w-full md:w-2/3 bg-gray-100 p-4 rounded">
                                        主要内容（移动端为全宽）
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">代码示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
&lt;div class="flex flex-col md:flex-row gap-4"&gt;
  &lt;div class="w-full md:w-1/3 bg-gray-100 p-4 rounded"&gt;
    侧边栏（移动端为全宽）
  &lt;/div&gt;
  &lt;div class="w-full md:w-2/3 bg-gray-100 p-4 rounded"&gt;
    主要内容（移动端为全宽）
  &lt;/div&gt;
&lt;/div&gt;</pre>
                        </div>
                    </div>
                </div>

                <!-- 响应式容器 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-3 text-indigo-500">2. 响应式容器</h3>
                    <p class="mb-4">Tailwind 的 <code>container</code> 类可以配合响应式断点使用。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div>
                            <h4 class="font-medium mb-2">示例:</h4>
                            <div class="bg-blue-50 p-4 rounded">
                                <div class="container mx-auto px-4 py-2 bg-blue-100 rounded text-center">
                                    容器宽度会根据屏幕尺寸变化
                                </div>
                            </div>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">配置示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
// tailwind.config.js
module.exports = {
  theme: {
    container: {
      center: true,
      padding: {
        DEFAULT: '1rem',
        sm: '2rem',
        lg: '4rem',
        xl: '5rem',
        '2xl': '6rem',
      },
    },
  },
}</pre>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto mt-2">
&lt;div class="container mx-auto"&gt;
  容器内容
&lt;/div&gt;</pre>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>

<script setup lang="ts">
// 组件中可以添加一些响应式行为的逻辑
import { ref, onMounted } from 'vue';

const screenSize = ref('未检测');

// 检测并显示当前屏幕尺寸
const updateScreenSize = () => {
  const width = window.innerWidth;
  if (width < 640) screenSize.value = '默认 (< 640px)';
  else if (width < 768) screenSize.value = 'sm (≥ 640px)';
  else if (width < 1024) screenSize.value = 'md (≥ 768px)';
  else if (width < 1280) screenSize.value = 'lg (≥ 1024px)';
  else if (width < 1536) screenSize.value = 'xl (≥ 1280px)';
  else screenSize.value = '2xl (≥ 1536px)';
};

onMounted(() => {
  updateScreenSize();
  window.addEventListener('resize', updateScreenSize);
});
</script>

<style scoped>
@import "tailwindcss";
/* 可以在这里添加打印样式的示例 */
@media print {
  .print-only {
    display: block !important;
  }

  .no-print {
    display: none !important;
  }
}

/* 也可以使用 @apply 和媒体查询结合 */
.responsive-heading {
  @apply text-lg;
}

@media (min-width: 768px) {
  .responsive-heading {
    @apply text-xl;
  }
}

@media (min-width: 1024px) {
  .responsive-heading {
    @apply text-2xl;
  }
}
</style>
