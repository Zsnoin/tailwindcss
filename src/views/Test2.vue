<template>
  <div class="container mx-auto px-4 py-8">
    <h1 class="text-3xl font-bold mb-8 text-center text-indigo-600 border-b pb-3">Tailwind CSS 布局功能指南</h1>

    <!-- 伪类 -->
    <section class="mb-12">
      <h2 class="text-2xl font-semibold mb-4 text-gray-800 border-l-4 border-indigo-500 pl-3">伪类</h2>
      <p class="mb-4 text-gray-600">Tailwind CSS 提供了各种伪类修饰符，用于处理不同状态下的样式。</p>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
        <div>
          <h3 class="text-xl font-medium mb-3 text-indigo-700">交互状态伪类</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <button class="mb-4 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded w-full">
              hover:bg-blue-700 (鼠标悬停)
            </button>

            <button class="mb-4 bg-green-500 active:bg-green-700 text-white font-bold py-2 px-4 rounded w-full">
              active:bg-green-700 (鼠标按下)
            </button>

            <button class="mb-4 bg-purple-500 focus:ring-4 focus:ring-purple-300 text-white font-bold py-2 px-4 rounded w-full">
              focus:ring-4 (获得焦点)
            </button>

            <div class="group bg-gray-200 p-3 rounded hover:bg-gray-300 cursor-pointer">
              <p>父元素 (group)</p>
              <p class="text-gray-500 group-hover:text-black">group-hover:text-black</p>
            </div>
          </div>
        </div>

        <div>
          <h3 class="text-xl font-medium mb-3 text-indigo-700">表单状态伪类</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <div class="mb-4">
              <label class="block text-gray-700 text-sm font-bold mb-2">禁用状态</label>
              <input class="disabled:bg-gray-200 disabled:text-gray-500 border rounded w-full py-2 px-3 text-gray-700" 
                     type="text" placeholder="禁用输入框" disabled>
            </div>

            <div class="mb-4">
              <label class="block text-gray-700 text-sm font-bold mb-2">可选/必填状态</label>
              <input class="required:border-red-500 optional:border-green-500 border rounded w-full py-2 px-3" 
                     type="text" placeholder="必填项" required>
            </div>

            <div class="mb-4">
              <label class="block text-gray-700 text-sm font-bold mb-2">有效/无效状态</label>
              <input class="valid:border-green-500 invalid:border-red-500 border rounded w-full py-2 px-3" 
                     type="email" placeholder="请输入有效邮箱" required>
            </div>
          </div>
        </div>
      </div>

      <div>
        <h3 class="text-xl font-medium mb-3 text-indigo-700">深色模式与奇偶行</h3>
        <div class="bg-gray-100 p-4 rounded-lg mb-6">
          <div class="dark:bg-gray-800 dark:text-white p-4 border border-dashed border-gray-400 mb-4">
            <p>dark:bg-gray-800 dark:text-white (深色模式)</p>
            <p class="text-sm text-gray-500 dark:text-gray-300">需要设置 dark 类或媒体查询</p>
          </div>

          <div class="space-y-2">
            <div class="odd:bg-white even:bg-gray-200 p-2">第一行 (odd)</div>
            <div class="odd:bg-white even:bg-gray-200 p-2">第二行 (even)</div>
            <div class="odd:bg-white even:bg-gray-200 p-2">第三行 (odd)</div>
            <div class="odd:bg-white even:bg-gray-200 p-2">第四行 (even)</div>
          </div>
        </div>
      </div>

      <div class="bg-indigo-50 p-4 rounded-lg border-l-4 border-indigo-500">
        <h4 class="font-medium mb-2">伪类修饰符用法:</h4>
        <pre class="bg-gray-800 text-green-300 p-3 rounded overflow-x-auto"><code>&lt;button class="bg-blue-500 hover:bg-blue-700"&gt;按钮&lt;/button&gt;
&lt;div class="group"&gt;
  &lt;p class="group-hover:text-red-500"&gt;父元素悬停时变红&lt;/p&gt;
&lt;/div&gt;
&lt;input class="focus:ring-2 focus:ring-blue-500"&gt;
&lt;div class="first:font-bold last:text-red-500"&gt;
  &lt;p&gt;第一个加粗&lt;/p&gt;
  &lt;p&gt;中间正常&lt;/p&gt;
  &lt;p&gt;最后一个红色&lt;/p&gt;
&lt;/div&gt;</code></pre>
      </div>
    </section>

    <!-- 伪元素 -->
    <section class="mb-12">
      <h2 class="text-2xl font-semibold mb-4 text-gray-800 border-l-4 border-indigo-500 pl-3">伪元素</h2>
      <p class="mb-4 text-gray-600">使用 before 和 after 伪元素为元素添加额外内容。</p>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
        <div>
          <h3 class="text-xl font-medium mb-3 text-indigo-700">基本伪元素</h3>
          <div class="bg-gray-100 p-4 rounded-lg space-y-6">
            <div class="relative before:content-[''] before:absolute before:w-4 before:h-full before:bg-blue-500 before:left-0">
              <p class="pl-6">左侧有蓝色条，使用 before 伪元素</p>
            </div>

            <div class="relative after:content-['→'] after:absolute after:right-4 after:text-red-500">
              <p>右侧有箭头，使用 after 伪元素</p>
            </div>

            <div class="relative before:content-['*'] before:absolute before:text-red-500 before:-left-4 before:top-0">
              <p>前面有星号，表示必填项</p>
            </div>
          </div>
        </div>

        <div>
          <h3 class="text-xl font-medium mb-3 text-indigo-700">创意伪元素用法</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <div class="relative inline-block mb-6">
              <div class="relative z-10 bg-white px-4 py-2 border border-gray-300 rounded">悬停查看提示</div>
              <div class="absolute z-20 hidden hover:block top-full left-0 mt-2 bg-black text-white p-2 rounded text-sm w-48 
                          before:content-[''] before:absolute before:-top-2 before:left-4 before:border-8 before:border-transparent before:border-b-black">
                这是使用伪元素创建的小三角形提示气泡
              </div>
            </div>

            <div class="relative pl-6 before:content-['✓'] before:absolute before:left-0 before:text-green-500 mb-2">
              已完成任务
            </div>

            <div class="relative pl-6 before:content-['✗'] before:absolute before:left-0 before:text-red-500 mb-2">
              未完成任务
            </div>

            <div class="relative inline-block after:content-['NEW'] after:bg-red-500 after:text-white after:text-xs 
                        after:px-1 after:ml-1 after:rounded">
              新功能标签
            </div>
          </div>
        </div>
      </div>

      <div class="bg-indigo-50 p-4 rounded-lg border-l-4 border-indigo-500 mb-4">
        <h4 class="font-medium mb-2">引用样式示例:</h4>
        <blockquote class="relative pl-8 py-2 italic text-gray-700
                          before:content-['\201C'] before:absolute before:top-0 before:left-0 before:text-4xl before:text-gray-400">
          这是一段引用文字，使用伪元素添加了引号标记，使布局更加美观。
        </blockquote>
      </div>

      <div class="bg-indigo-50 p-4 rounded-lg border-l-4 border-indigo-500">
        <h4 class="font-medium mb-2">伪元素代码示例:</h4>
        <pre class="bg-gray-800 text-green-300 p-3 rounded overflow-x-auto"><code>&lt;div class="before:content-[''] before:absolute before:left-0 before:w-1 before:h-full before:bg-blue-500"&gt;
  左侧有蓝色条
&lt;/div&gt;

&lt;div class="after:content-['→'] after:ml-2 after:text-red-500"&gt;
  文字后有箭头
&lt;/div&gt;

&lt;blockquote class="before:content-['\201C'] before:text-4xl before:text-gray-400"&gt;
  引用文字
&lt;/blockquote&gt;</code></pre>
      </div>
    </section>

    <!-- Flexbox布局 -->
    <section class="mb-12">
      <h2 class="text-2xl font-semibold mb-4 text-gray-800 border-l-4 border-indigo-500 pl-3">Flexbox 布局</h2>
      <p class="mb-4 text-gray-600">Flexbox 是一维布局系统，适用于行或列的布局。</p>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
        <div>
          <h3 class="text-xl font-medium mb-3 text-indigo-700">Flex 容器属性</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <h4 class="font-medium mb-2">flex-direction</h4>
            <div class="mb-4">
              <div class="flex flex-row bg-gray-200 p-2 mb-2">
                <div class="bg-blue-500 text-white p-2 m-1">1</div>
                <div class="bg-blue-500 text-white p-2 m-1">2</div>
                <div class="bg-blue-500 text-white p-2 m-1">3</div>
              </div>
              <p class="text-sm text-gray-600">flex flex-row (默认，水平方向)</p>
            </div>

            <div class="mb-4">
              <div class="flex flex-col bg-gray-200 p-2 mb-2">
                <div class="bg-green-500 text-white p-2 m-1">1</div>
                <div class="bg-green-500 text-white p-2 m-1">2</div>
                <div class="bg-green-500 text-white p-2 m-1">3</div>
              </div>
              <p class="text-sm text-gray-600">flex flex-col (垂直方向)</p>
            </div>

            <h4 class="font-medium mb-2">justify-content</h4>
            <div class="space-y-2 mb-4">
              <div class="flex justify-start bg-gray-200 p-2">
                <div class="bg-purple-500 text-white p-2 m-1">1</div>
                <div class="bg-purple-500 text-white p-2 m-1">2</div>
                <div class="bg-purple-500 text-white p-2 m-1">3</div>
              </div>
              <div class="flex justify-center bg-gray-200 p-2">
                <div class="bg-purple-500 text-white p-2 m-1">1</div>
                <div class="bg-purple-500 text-white p-2 m-1">2</div>
                <div class="bg-purple-500 text-white p-2 m-1">3</div>
              </div>
              <div class="flex justify-end bg-gray-200 p-2">
                <div class="bg-purple-500 text-white p-2 m-1">1</div>
                <div class="bg-purple-500 text-white p-2 m-1">2</div>
                <div class="bg-purple-500 text-white p-2 m-1">3</div>
              </div>
              <div class="flex justify-between bg-gray-200 p-2">
                <div class="bg-purple-500 text-white p-2 m-1">1</div>
                <div class="bg-purple-500 text-white p-2 m-1">2</div>
                <div class="bg-purple-500 text-white p-2 m-1">3</div>
              </div>
            </div>
          </div>
        </div>

        <div>
          <h3 class="text-xl font-medium mb-3 text-indigo-700">对齐和间距</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <h4 class="font-medium mb-2">align-items</h4>
            <div class="flex items-start h-24 bg-gray-200 p-2 mb-4">
              <div class="bg-red-500 text-white p-2 m-1">start</div>
              <div class="bg-red-500 text-white p-2 m-1 h-12">start</div>
              <div class="bg-red-500 text-white p-2 m-1">start</div>
            </div>
            <div class="flex items-center h-24 bg-gray-200 p-2 mb-4">
              <div class="bg-red-500 text-white p-2 m-1">center</div>
              <div class="bg-red-500 text-white p-2 m-1 h-12">center</div>
              <div class="bg-red-500 text-white p-2 m-1">center</div>
            </div>

            <h4 class="font-medium mb-2">flex-wrap</h4>
            <div class="flex flex-wrap bg-gray-200 p-2 mb-4">
              <div class="bg-teal-500 text-white p-2 m-1 w-1/3">1</div>
              <div class="bg-teal-500 text-white p-2 m-1 w-1/3">2</div>
              <div class="bg-teal-500 text-white p-2 m-1 w-1/3">3</div>
              <div class="bg-teal-500 text-white p-2 m-1 w-1/3">4</div>
              <div class="bg-teal-500 text-white p-2 m-1 w-1/3">5</div>
            </div>

            <h4 class="font-medium mb-2">gap</h4>
            <div class="flex gap-4 bg-gray-200 p-2">
              <div class="bg-amber-500 text-white p-2">1</div>
              <div class="bg-amber-500 text-white p-2">2</div>
              <div class="bg-amber-500 text-white p-2">3</div>
            </div>
          </div>
        </div>
      </div>

      <div>
        <h3 class="text-xl font-medium mb-3 text-indigo-700">Flex 项目属性</h3>
        <div class="bg-gray-100 p-4 rounded-lg mb-6">
          <div class="flex bg-gray-200 p-2 mb-4">
            <div class="bg-indigo-500 text-white p-2 m-1 flex-1">flex-1</div>
            <div class="bg-indigo-500 text-white p-2 m-1 flex-2">flex-2</div>
            <div class="bg-indigo-500 text-white p-2 m-1 flex-1">flex-1</div>
          </div>

          <div class="flex bg-gray-200 p-2 mb-4">
            <div class="bg-pink-500 text-white p-2 m-1">固定宽度</div>
            <div class="bg-pink-500 text-white p-2 m-1 flex-grow">flex-grow</div>
            <div class="bg-pink-500 text-white p-2 m-1">固定宽度</div>
          </div>

          <div class="flex bg-gray-200 p-2">
            <div class="bg-orange-500 text-white p-2 m-1">1</div>
            <div class="bg-orange-500 text-white p-2 m-1">2</div>
            <div class="bg-orange-500 text-white p-2 m-1 flex-none">flex-none</div>
            <div class="bg-orange-500 text-white p-2 m-1 flex-grow">flex-grow</div>
          </div>
        </div>
      </div>

      <div class="bg-indigo-50 p-4 rounded-lg border-l-4 border-indigo-500">
        <h4 class="font-medium mb-2">实际布局案例:</h4>
        <div class="bg-white p-4 rounded shadow-sm mb-4">
          <div class="flex flex-col md:flex-row">
            <div class="md:w-1/3 p-2">
              <div class="bg-gray-200 h-full p-4">侧边栏</div>
            </div>
            <div class="md:w-2/3 p-2">
              <div class="bg-gray-100 h-full p-4">
                <div class="font-bold mb-2">主要内容区</div>
                <p>使用flex布局，在移动设备上垂直排列，在桌面设备上水平排列</p>
              </div>
            </div>
          </div>
        </div>

        <h4 class="font-medium mb-2">Flex 代码示例:</h4>
        <pre class="bg-gray-800 text-green-300 p-3 rounded overflow-x-auto"><code>&lt;div class="flex justify-between items-center"&gt;
  &lt;div&gt;左对齐&lt;/div&gt;
  &lt;div&gt;右对齐&lt;/div&gt;
&lt;/div&gt;

&lt;div class="flex flex-col md:flex-row gap-4"&gt;
  &lt;div class="md:w-1/3"&gt;侧边栏&lt;/div&gt;
  &lt;div class="md:w-2/3"&gt;主要内容区&lt;/div&gt;
&lt;/div&gt;

&lt;div class="flex"&gt;
  &lt;div class="flex-none w-16"&gt;固定宽度&lt;/div&gt;
  &lt;div class="flex-grow"&gt;自动填充&lt;/div&gt;
  &lt;div class="flex-none w-16"&gt;固定宽度&lt;/div&gt;
&lt;/div&gt;</code></pre>
      </div>
    </section>

    <!-- Grid布局 -->
    <section class="mb-12">
      <h2 class="text-2xl font-semibold mb-4 text-gray-800 border-l-4 border-indigo-500 pl-3">Grid 布局</h2>
      <p class="mb-4 text-gray-600">Grid 是二维布局系统，同时控制行和列。</p>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
        <div>
          <h3 class="text-xl font-medium mb-3 text-indigo-700">基本网格</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <h4 class="font-medium mb-2">grid-cols-*</h4>
            <div class="grid grid-cols-3 gap-2 mb-4">
              <div class="bg-blue-500 text-white p-2 text-center">1</div>
              <div class="bg-blue-500 text-white p-2 text-center">2</div>
              <div class="bg-blue-500 text-white p-2 text-center">3</div>
              <div class="bg-blue-500 text-white p-2 text-center">4</div>
              <div class="bg-blue-500 text-white p-2 text-center">5</div>
              <div class="bg-blue-500 text-white p-2 text-center">6</div>
            </div>
            <p class="text-sm text-gray-600 mb-4">grid grid-cols-3 gap-2 (3列网格)</p>

            <h4 class="font-medium mb-2">grid-rows-*</h4>
            <div class="grid grid-cols-3 grid-rows-2 gap-2 h-32 mb-4">
              <div class="bg-green-500 text-white p-2 text-center">1</div>
              <div class="bg-green-500 text-white p-2 text-center">2</div>
              <div class="bg-green-500 text-white p-2 text-center">3</div>
              <div class="bg-green-500 text-white p-2 text-center">4</div>
              <div class="bg-green-500 text-white p-2 text-center">5</div>
              <div class="bg-green-500 text-white p-2 text-center">6</div>
            </div>
            <p class="text-sm text-gray-600">grid grid-cols-3 grid-rows-2 (3列2行)</p>
          </div>
        </div>

        <div>
          <h3 class="text-xl font-medium mb-3 text-indigo-700">网格跨列跨行</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <div class="grid grid-cols-3 gap-2 mb-6">
              <div class="bg-purple-500 text-white p-2 text-center col-span-2">col-span-2</div>
              <div class="bg-purple-500 text-white p-2 text-center">1</div>
              <div class="bg-purple-500 text-white p-2 text-center">1</div>
              <div class="bg-purple-500 text-white p-2 text-center col-span-2">col-span-2</div>
            </div>

            <div class="grid grid-cols-3 grid-rows-3 gap-2 h-48 mb-2">
              <div class="bg-pink-500 text-white p-2 text-center">1</div>
              <div class="bg-pink-500 text-white p-2 text-center">2</div>
              <div class="bg-pink-500 text-white p-2 text-center row-span-2">row-span-2</div>
              <div class="bg-pink-500 text-white p-2 text-center">4</div>
              <div class="bg-pink-500 text-white p-2 text-center">5</div>
              <div class="bg-pink-500 text-white p-2 text-center col-span-2">col-span-2</div>
              <div class="bg-pink-500 text-white p-2 text-center">8</div>
            </div>
          </div>
        </div>
      </div>

      <div>
        <h3 class="text-xl font-medium mb-3 text-indigo-700">自动网格与响应式</h3>
        <div class="bg-gray-100 p-4 rounded-lg mb-6">
          <h4 class="font-medium mb-2">自动填充列 (grid-cols-auto-*)</h4>
          <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 mb-6">
            <div class="bg-teal-500 text-white p-4 text-center">响应式列</div>
            <div class="bg-teal-500 text-white p-4 text-center">响应式列</div>
            <div class="bg-teal-500 text-white p-4 text-center">响应式列</div>
            <div class="bg-teal-500 text-white p-4 text-center">响应式列</div>
            <div class="bg-teal-500 text-white p-4 text-center">响应式列</div>
            <div class="bg-teal-500 text-white p-4 text-center">响应式列</div>
          </div>
          <p class="text-sm text-gray-600 mb-4">grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4</p>

          <h4 class="font-medium mb-2">自动行列 (grid-flow-*)</h4>
          <div class="grid grid-flow-col auto-cols-fr gap-2 mb-6">
            <div class="bg-amber-500 text-white p-2 text-center">自动列宽</div>
            <div class="bg-amber-500 text-white p-2 text-center">自动列宽</div>
            <div class="bg-amber-500 text-white p-2 text-center">自动列宽</div>
          </div>
          <p class="text-sm text-gray-600">grid grid-flow-col auto-cols-fr</p>
        </div>
      </div>

      <div class="bg-indigo-50 p-4 rounded-lg border-l-4 border-indigo-500">
        <h4 class="font-medium mb-2">图片画廊示例:</h4>
        <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mb-4">
          <div class="bg-gray-300 aspect-square"></div>
          <div class="bg-gray-400 aspect-square md:col-span-2 md:row-span-2"></div>
          <div class="bg-gray-300 aspect-square"></div>
          <div class="bg-gray-300 aspect-square"></div>
          <div class="bg-gray-300 aspect-square"></div>
          <div class="bg-gray-300 aspect-square"></div>
        </div>

        <h4 class="font-medium mb-2">Grid 代码示例:</h4>
        <pre class="bg-gray-800 text-green-300 p-3 rounded overflow-x-auto"><code>&lt;!-- 基本网格 --&gt;
&lt;div class="grid grid-cols-3 gap-4"&gt;
  &lt;div&gt;Item 1&lt;/div&gt;
  &lt;div&gt;Item 2&lt;/div&gt;
  &lt;div&gt;Item 3&lt;/div&gt;
&lt;/div&gt;

&lt;!-- 响应式网格 --&gt;
&lt;div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4"&gt;
  &lt;div&gt;在小屏幕上是1列，中等屏幕2列，大屏幕3列&lt;/div&gt;
&lt;/div&gt;

&lt;!-- 跨行跨列 --&gt;
&lt;div class="grid grid-cols-3 gap-4"&gt;
  &lt;div class="col-span-2"&gt;跨2列&lt;/div&gt;
  &lt;div class="row-span-2"&gt;跨2行&lt;/div&gt;
  &lt;div class="col-span-2 row-span-2"&gt;跨2行2列&lt;/div&gt;
&lt;/div&gt;</code></pre>
      </div>
    </section>

    <!-- 定位 -->
    <section class="mb-12">
      <h2 class="text-2xl font-semibold mb-4 text-gray-800 border-l-4 border-indigo-500 pl-3">定位 (Position)</h2>
      <p class="mb-4 text-gray-600">控制元素在页面上的精确位置。</p>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
        <div>
          <h3 class="text-xl font-medium mb-3 text-indigo-700">基本定位</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <div class="relative bg-white border p-4 mb-6 h-32">
              <div class="absolute top-0 left-0 bg-red-500 text-white p-1 text-xs">
                absolute top-0 left-0
              </div>
              <div class="absolute top-0 right-0 bg-blue-500 text-white p-1 text-xs">
                absolute top-0 right-0
              </div>
              <div class="absolute bottom-0 left-0 bg-green-500 text-white p-1 text-xs">
                absolute bottom-0 left-0
              </div>
              <div class="absolute bottom-0 right-0 bg-yellow-500 text-white p-1 text-xs">
                absolute bottom-0 right-0
              </div>
              <div class="absolute inset-x-0 top-1/2 -translate-y-1/2 text-center bg-purple-500 text-white p-1 text-xs">
                absolute inset-x-0 top-1/2
              </div>
            </div>

            <div class="relative bg-white border p-4 mb-6 h-20">
              <p>使用 relative 的父容器</p>
              <div class="absolute -top-2 -right-2 bg-red-500 text-white rounded-full w-6 h-6 flex items-center justify-center text-xs">
                5
              </div>
            </div>

            <div class="relative bg-white border p-4 mb-6 h-20">
              <div class="absolute inset-0 bg-blue-200 opacity-50"></div>
              <p class="relative z-10">使用 inset-0 填充整个容器</p>
            </div>
          </div>
        </div>

        <div>
          <h3 class="text-xl font-medium mb-3 text-indigo-700">固定和粘性定位</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <div class="mb-4">
              <div class="relative bg-white border p-4 h-40 overflow-auto">
                <div class="sticky top-0 bg-yellow-400 p-2 mb-2 z-10">
                  sticky top-0 (滚动时固定在顶部)
                </div>
                <div class="h-20 bg-gray-200 mb-2"></div>
                <div class="h-20 bg-gray-200 mb-2"></div>
                <div class="h-20 bg-gray-200"></div>
              </div>
            </div>

            <div class="mb-4">
              <div class="relative bg-white border p-4 h-40">
                <p>fixed 定位会相对于视口固定位置</p>
                <p class="text-sm text-gray-500">在实际使用中，可以用于固定导航栏、返回顶部按钮等</p>
                <div class="fixed bottom-4 right-4 bg-blue-500 text-white p-2 rounded-full text-xs hidden md:block">
                  fixed 示例 (实际效果在页面右下角)
                </div>
              </div>
            </div>

            <div class="relative bg-white border p-4 h-28">
              <p>z-index 控制叠加层级</p>
              <div class="absolute left-8 top-8 w-16 h-16 bg-blue-500 z-10"></div>
              <div class="absolute left-12 top-12 w-16 h-16 bg-red-500 z-20"></div>
              <div class="absolute left-16 top-16 w-16 h-16 bg-green-500 z-30"></div>
            </div>
          </div>
        </div>
      </div>

      <div class="bg-indigo-50 p-4 rounded-lg border-l-4 border-indigo-500">
        <h4 class="font-medium mb-2">定位案例 - 卡片徽章:</h4>
        <div class="relative inline-block mb-6">
          <div class="bg-white rounded-lg shadow-lg p-4 w-64">
            <div class="text-lg font-bold mb-2">产品名称</div>
            <p class="text-gray-600">产品描述信息</p>
          </div>
          <div class="absolute -top-3 -right-3 bg-red-500 text-white rounded-full w-8 h-8 flex items-center justify-center font-bold">
            新
          </div>
        </div>

        <h4 class="font-medium mb-2">定位代码示例:</h4>
        <pre class="bg-gray-800 text-green-300 p-3 rounded overflow-x-auto"><code>&lt;!-- 绝对定位 --&gt;
&lt;div class="relative"&gt;
  &lt;div class="absolute top-0 right-0"&gt;右上角&lt;/div&gt;
  &lt;div class="absolute inset-0 bg-black opacity-50"&gt;覆盖整个容器&lt;/div&gt;
&lt;/div&gt;

&lt;!-- 粘性定位 --&gt;
&lt;div class="sticky top-0 bg-white shadow z-10"&gt;
  粘性导航栏
&lt;/div&gt;

&lt;!-- 固定定位 --&gt;
&lt;button class="fixed bottom-4 right-4 bg-blue-500 rounded-full"&gt;
  返回顶部
&lt;/button&gt;</code></pre>
      </div>
    </section>

    <div class="text-center text-gray-500 mt-12 mb-6">
      <p>Tailwind CSS 提供了全面的布局工具，帮助开发者快速构建各种复杂的界面。</p>
      <p class="mt-2">查看 <a href="https://tailwindcss.com/docs" target="_blank" class="text-blue-600 hover:underline">官方文档</a> 了解更多详细信息。</p>
    </div>
  </div>
</template>

<script setup lang="ts">
// 无需额外脚本逻辑
</script>

<style scoped>
/* Tailwind 已提供所有所需样式 */
</style>