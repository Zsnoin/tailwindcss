<template>
    <div class="container mx-auto py-8 px-4 max-w-6xl">
        <h1 class="text-3xl font-bold mb-8 text-center text-indigo-700">Tailwind CSS 4.0 进阶特性</h1>

        <!-- 样式复用部分 -->
        <section class="mb-12 bg-white rounded-lg shadow-md p-6">
            <h2 class="text-2xl font-semibold mb-4 text-indigo-600 border-b pb-2">样式复用</h2>

            <div class="space-y-4">
                <p class="text-gray-700">Tailwind CSS 提供多种方式来复用样式，避免重复编写相同的类名组合。</p>

                <!-- 方法1: @apply 指令 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-2 text-indigo-500">1. 使用 @apply 指令</h3>
                    <p class="mb-2">通过 @apply 指令，可以在 CSS 中复用 Tailwind 类。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <h4 class="font-medium mb-2">实际效果：</h4>
                            <button class="btn-primary">主要按钮</button>
                            <button class="btn-secondary ml-2">次要按钮</button>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">代码示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
.btn-primary {
  @apply bg-blue-500 hover:bg-blue-700 text-white 
         font-bold py-2 px-4 rounded;
}

.btn-secondary {
  @apply bg-gray-300 hover:bg-gray-400 text-gray-800 
         font-bold py-2 px-4 rounded;
}</pre>
                        </div>
                    </div>
                </div>

                <!-- 方法2: 提取组件 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-2 text-indigo-500">2. 提取组件</h3>
                    <p class="mb-2">创建可复用的 Vue 组件，封装常用的 UI 元素。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <h4 class="font-medium mb-2">实际效果：</h4>
                            <div class="card">
                                <h3 class="card-title">卡片标题</h3>
                                <p class="card-body">这是卡片内容，展示了组件的复用方式。</p>
                            </div>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">代码示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
&lt;!-- Card.vue --&gt;
&lt;template&gt;
  &lt;div class="bg-white rounded-lg shadow-md p-4"&gt;
    &lt;slot&gt;&lt;/slot&gt;
  &lt;/div&gt;
&lt;/template&gt;

&lt;!-- 使用方式 --&gt;
&lt;Card&gt;
  &lt;h3 class="text-xl font-medium"&gt;卡片标题&lt;/h3&gt;
  &lt;p class="mt-2"&gt;卡片内容&lt;/p&gt;
&lt;/Card&gt;</pre>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 自定义指令部分 -->
        <section class="mb-12 bg-white rounded-lg shadow-md p-6">
            <h2 class="text-2xl font-semibold mb-4 text-indigo-600 border-b pb-2">自定义指令</h2>

            <div class="space-y-4">
                <p class="text-gray-700">Tailwind CSS 允许自定义指令，扩展原有功能或创建新功能。</p>

                <!-- 自定义变体 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-2 text-indigo-500">1. 自定义变体</h3>
                    <p class="mb-2">可以创建自定义状态变体，如 <code>custom-hover:</code>, <code>parent-active:</code> 等。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <h4 class="font-medium mb-2">实际效果：</h4>
                            <div class="group p-4 border border-gray-300 rounded">
                                <p>鼠标悬停在此区域</p>
                                <span class="text-gray-500 group-hover:text-green-500">使用 group-hover 变体</span>
                            </div>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">配置示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
// tailwind.config.js
module.exports = {
  variants: {
    extend: {
      backgroundColor: ['active'],
      textColor: ['visited', 'group-hover'],
    }
  }
}</pre>
                        </div>
                    </div>
                </div>

                <!-- 添加新指令 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-2 text-indigo-500">2. 添加新指令</h3>
                    <p class="mb-2">通过插件系统添加全新的实用指令。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <h4 class="font-medium mb-2">自定义阴影效果：</h4>
                            <div class="p-4 bg-white custom-shadow rounded">
                                具有自定义阴影效果的元素
                            </div>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">插件示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
// 添加自定义阴影插件
const plugin = require('tailwindcss/plugin')

module.exports = {
  plugins: [
    plugin(function({ addUtilities }) {
      const newUtilities = {
        '.custom-shadow': {
          boxShadow: '0 0 15px rgba(0, 0, 255, 0.2)'
        }
      }
      addUtilities(newUtilities)
    })
  ]
}</pre>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 自定义函数部分 -->
        <section class="mb-12 bg-white rounded-lg shadow-md p-6">
            <h2 class="text-2xl font-semibold mb-4 text-indigo-600 border-b pb-2">自定义函数</h2>

            <div class="space-y-4">
                <p class="text-gray-700">在 Tailwind 配置中，可以使用 JavaScript 函数动态生成样式。</p>

                <!-- 动态生成颜色 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-2 text-indigo-500">1. 动态生成颜色变体</h3>
                    <p class="mb-2">使用函数根据基础颜色生成色阶。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <h4 class="font-medium mb-2">颜色示例：</h4>
                            <div class="flex space-x-2">
                                <div class="w-12 h-12 rounded bg-brand"></div>
                                <div class="w-12 h-12 rounded bg-brand-light"></div>
                                <div class="w-12 h-12 rounded bg-brand-dark"></div>
                            </div>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">配置示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
// tailwind.config.js
const Color = require('color')

module.exports = {
  theme: {
    extend: {
      colors: {
        'brand': '#3366FF',
        'brand-light': Color('#3366FF').lighten(0.2).hex(),
        'brand-dark': Color('#3366FF').darken(0.2).hex(),
      }
    }
  }
}</pre>
                        </div>
                    </div>
                </div>

                <!-- 动态间距缩放 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-2 text-indigo-500">2. 动态间距缩放</h3>
                    <p class="mb-2">创建自定义间距比例函数。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <h4 class="font-medium mb-2">示例间距：</h4>
                            <div class="space-y-2">
                                <div class="p-scale-1 bg-blue-100 text-center">p-scale-1</div>
                                <div class="p-scale-2 bg-blue-200 text-center">p-scale-2</div>
                                <div class="p-scale-3 bg-blue-300 text-center">p-scale-3</div>
                            </div>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">配置示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      padding: {
        // 使用函数生成按比例缩放的间距
        'scale-1': '0.5rem',
        'scale-2': '1rem',
        'scale-3': '2rem',
        // 也可以动态计算: i => `${i * 0.5}rem`
      }
    }
  }
}</pre>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 自定义样式部分 -->
        <section class="mb-12 bg-white rounded-lg shadow-md p-6">
            <h2 class="text-2xl font-semibold mb-4 text-indigo-600 border-b pb-2">自定义样式</h2>

            <div class="space-y-4">
                <p class="text-gray-700">通过扩展 Tailwind 配置，可以添加自己的自定义样式。</p>

                <!-- 自定义主题 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-2 text-indigo-500">1. 自定义主题颜色</h3>
                    <p class="mb-2">扩展 Tailwind 主题颜色。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <h4 class="font-medium mb-2">颜色示例：</h4>
                            <div class="flex flex-wrap gap-2">
                                <div class="w-12 h-12 rounded bg-primary"></div>
                                <div class="w-12 h-12 rounded bg-secondary"></div>
                                <div class="w-12 h-12 rounded bg-accent"></div>
                            </div>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">配置示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        'primary': '#3366FF',
        'secondary': '#FF6633',
        'accent': '#33FF66',
      }
    }
  }
}</pre>
                        </div>
                    </div>
                </div>

                <!-- 自定义断点 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-2 text-indigo-500">2. 自定义响应式断点</h3>
                    <p class="mb-2">定制自己的断点尺寸。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <h4 class="font-medium mb-2">响应示例：</h4>
                            <div class="w-full bg-blue-100 p-2">
                                <p class="text-xs xs:text-sm sm:text-base md:text-lg lg:text-xl xl:text-2xl">
                                    响应式文本大小
                                </p>
                            </div>
                        </div>

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
    }
  }
}</pre>
                        </div>
                    </div>
                </div>

                <!-- 自定义字体 -->
                <div class="bg-gray-50 p-4 rounded-lg">
                    <h3 class="text-lg font-medium mb-2 text-indigo-500">3. 自定义字体</h3>
                    <p class="mb-2">添加自定义字体家族和字体大小。</p>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <h4 class="font-medium mb-2">字体示例：</h4>
                            <div class="space-y-2">
                                <p class="font-main text-xl">自定义主要字体</p>
                                <p class="font-special text-xl">特殊显示字体</p>
                            </div>
                        </div>

                        <div>
                            <h4 class="font-medium mb-2">配置示例：</h4>
                            <pre class="bg-gray-800 text-white p-4 rounded text-sm overflow-x-auto">
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      fontFamily: {
        'main': ['Roboto', 'sans-serif'],
        'special': ['Playfair Display', 'serif'],
      },
      fontSize: {
        'tiny': '0.625rem',
        'huge': '4rem',
      }
    }
  }
}</pre>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <div class="p-4 bg-yellow-50 border-l-4 border-yellow-400 rounded">
            <p class="text-yellow-700">
                <strong>提示：</strong> 所有这些自定义配置需要在 <code>tailwind.config.js</code> 文件中进行，
                然后运行构建过程使更改生效。确保你的项目正确配置了 PostCSS 和 Tailwind CSS。
            </p>
        </div>
    </div>
</template>

<script setup lang="ts">
// 可以在这里添加交互逻辑
</script>

<style scoped>
@import "tailwindcss";
/* 使用 @apply 示例 */
.btn-primary {
    @apply bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded transition-colors duration-200;
}

.btn-secondary {
    @apply bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-2 px-4 rounded transition-colors duration-200;
}

/* 卡片样式 */
.card {
    @apply bg-white rounded-lg shadow-md p-4 border border-gray-200;
}

.card-title {
    @apply text-xl font-medium mb-2 text-gray-800;
}

.card-body {
    @apply text-gray-600;
}

/* 自定义阴影效果 */
.custom-shadow {
    box-shadow: 0 0 15px rgba(0, 0, 255, 0.2);
}

/* 演示品牌颜色 */
.bg-brand {
    background-color: #3366FF;
}

.bg-brand-light {
    background-color: #6690FF;
}

.bg-brand-dark {
    background-color: #0033CC;
}

/* 演示主题颜色 */
.bg-primary {
    background-color: #3366FF;
}

.bg-secondary {
    background-color: #FF6633;
}

.bg-accent {
    background-color: #33FF66;
}

/* 演示间距缩放 */
.p-scale-1 {
    padding: 0.5rem;
}

.p-scale-2 {
    padding: 1rem;
}

.p-scale-3 {
    padding: 2rem;
}

/* 其他自定义样式可以放在这里 */
</style>
