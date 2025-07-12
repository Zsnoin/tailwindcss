<template>
  <div class="container mx-auto px-4 py-6">
    <h1 class="text-3xl font-bold mb-8 text-center text-blue-600 border-b pb-3">Tailwind CSS 基础指南</h1>

    <!-- 宽度和高度 -->
    <section class="mb-12">
      <h2 class="text-2xl font-semibold mb-4 text-gray-800 border-l-4 border-blue-500 pl-3">宽度和高度</h2>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-4">
        <div>
          <h3 class="text-xl font-medium mb-3 text-blue-700">宽度 (w-*)</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <h4 class="font-medium mb-2">固定宽度</h4>
            <div class="space-y-2 mb-4">
              <div class="w-12 bg-blue-200 p-2 text-center">w-12</div>
              <div class="w-24 bg-blue-300 p-2 text-center">w-24</div>
              <div class="w-36 bg-blue-400 p-2 text-center">w-36</div>
              <div class="w-48 bg-blue-500 p-2 text-center text-white">w-48</div>
            </div>
            <p class="text-sm text-gray-600 mb-2">单位转换: 1 = 0.25rem = 4px (默认)</p>
            <table class="w-full text-sm mb-4">
              <thead>
                <tr class="bg-gray-200">
                  <th class="p-2 text-left">类名</th>
                  <th class="p-2 text-left">rem</th>
                  <th class="p-2 text-left">px</th>
                </tr>
              </thead>
              <tbody>
                <tr><td class="p-2">w-1</td><td class="p-2">0.25rem</td><td class="p-2">4px</td></tr>
                <tr><td class="p-2">w-4</td><td class="p-2">1rem</td><td class="p-2">16px</td></tr>
                <tr><td class="p-2">w-16</td><td class="p-2">4rem</td><td class="p-2">64px</td></tr>
                <tr><td class="p-2">w-24</td><td class="p-2">6rem</td><td class="p-2">96px</td></tr>
              </tbody>
            </table>

            <h4 class="font-medium mb-2">百分比宽度</h4>
            <div class="space-y-2 mb-4">
              <div class="w-full bg-indigo-200 p-2 text-center">w-full (100%)</div>
              <div class="w-1/2 bg-indigo-300 p-2 text-center">w-1/2 (50%)</div>
              <div class="w-1/3 bg-indigo-400 p-2 text-center">w-1/3 (33.33%)</div>
              <div class="w-1/4 bg-indigo-500 p-2 text-center text-white">w-1/4 (25%)</div>
              <div class="w-1/5 bg-indigo-600 p-2 text-center text-white">w-1/5 (20%)</div>
            </div>

            <h4 class="font-medium mb-2">自定义宽度</h4>
            <div class="w-[250px] bg-purple-400 p-2 text-center mb-2">w-[250px]</div>
            <div class="w-[80%] bg-purple-500 p-2 text-center text-white">w-[80%]</div>
          </div>
        </div>

        <div>
          <h3 class="text-xl font-medium mb-3 text-blue-700">高度 (h-*)</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <h4 class="font-medium mb-2">固定高度</h4>
            <div class="flex items-end mb-4 h-48 bg-gray-200 p-2">
              <div class="h-12 w-16 bg-green-200 text-center mr-2">h-12</div>
              <div class="h-24 w-16 bg-green-300 text-center mr-2">h-24</div>
              <div class="h-36 w-16 bg-green-400 text-center mr-2">h-36</div>
              <div class="h-48 w-16 bg-green-500 text-white text-center">h-48</div>
            </div>

            <h4 class="font-medium mb-2">百分比和视口高度</h4>
            <div class="flex items-end mb-4 h-32 bg-gray-200 p-2">
              <div class="h-full w-20 bg-teal-300 text-center mr-2">h-full</div>
              <div class="h-1/2 w-20 bg-teal-400 text-center mr-2">h-1/2</div>
              <div class="h-24 w-20 bg-teal-500 text-white text-center">h-24</div>
            </div>
            <p class="text-sm text-gray-600">视口高度: h-screen = 100vh (视口高度)</p>

            <h4 class="font-medium mb-2">最小/最大高度</h4>
            <div class="min-h-[50px] bg-pink-300 p-2 text-center mb-2">min-h-[50px]</div>
            <div class="max-h-32 overflow-auto bg-pink-400 p-2 text-center">
              max-h-32 (内容超出时滚动)
              <div class="h-48"></div>
            </div>
          </div>
        </div>
      </div>

      <div class="bg-blue-50 p-4 rounded-lg border-l-4 border-blue-500">
        <h4 class="font-medium mb-2">代码示例:</h4>
        <pre class="bg-gray-800 text-green-300 p-3 rounded overflow-x-auto"><code>&lt;div class="w-full md:w-1/2 lg:w-1/3"&gt;响应式宽度&lt;/div&gt;
&lt;div class="h-64"&gt;高度为16rem (64px × 4)&lt;/div&gt;
&lt;div class="min-h-screen"&gt;至少占满整个视口高度&lt;/div&gt;
&lt;div class="w-[250px] h-[180px]"&gt;自定义精确尺寸&lt;/div&gt;</code></pre>
      </div>
    </section>

    <!-- 边距 -->
    <section class="mb-12">
      <h2 class="text-2xl font-semibold mb-4 text-gray-800 border-l-4 border-blue-500 pl-3">边距 (Margin & Padding)</h2>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-4">
        <div>
          <h3 class="text-xl font-medium mb-3 text-blue-700">内边距 (p-*)</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <h4 class="font-medium mb-2">基本内边距</h4>
            <div class="bg-yellow-100 border border-dashed border-yellow-400 mb-4">
              <div class="p-0 bg-yellow-200 mb-2 text-center">p-0 (无内边距)</div>
              <div class="p-2 bg-yellow-300 mb-2 text-center">p-2 (0.5rem = 8px)</div>
              <div class="p-4 bg-yellow-400 mb-2 text-center">p-4 (1rem = 16px)</div>
              <div class="p-8 bg-yellow-500 text-white text-center">p-8 (2rem = 32px)</div>
            </div>

            <h4 class="font-medium mb-2">方向性内边距</h4>
            <div class="space-y-3 mb-4">
              <div class="px-8 bg-orange-200 border border-dashed border-orange-400 text-center">px-8 (水平内边距)</div>
              <div class="py-4 bg-orange-300 border border-dashed border-orange-400 text-center">py-4 (垂直内边距)</div>
              <div class="pt-6 bg-orange-400 border border-dashed border-orange-400 text-center">pt-6 (顶部内边距)</div>
              <div class="pr-8 bg-orange-500 border border-dashed border-orange-400 text-center text-white">pr-8 (右侧内边距)</div>
              <div class="pb-4 bg-orange-600 border border-dashed border-orange-400 text-center text-white">pb-4 (底部内边距)</div>
              <div class="pl-10 bg-orange-700 border border-dashed border-orange-400 text-center text-white">pl-10 (左侧内边距)</div>
            </div>
          </div>
        </div>

        <div>
          <h3 class="text-xl font-medium mb-3 text-blue-700">外边距 (m-*)</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <h4 class="font-medium mb-2">基本外边距</h4>
            <div class="bg-blue-100 p-2 space-y-2">
              <div class="bg-blue-200 text-center">参考元素</div>
              <div class="m-0 bg-blue-300 text-center">m-0 (无外边距)</div>
              <div class="m-4 bg-blue-400 text-center">m-4 (1rem = 16px)</div>
              <div class="m-8 bg-blue-500 text-white text-center">m-8 (2rem = 32px)</div>
            </div>

            <h4 class="font-medium mt-4 mb-2">方向性外边距</h4>
            <div class="bg-red-100 p-2">
              <div class="mx-auto w-1/2 bg-red-300 text-center mb-3">mx-auto (水平居中)</div>
              <div class="my-4 bg-red-400 text-center">my-4 (垂直外边距)</div>
            </div>

            <h4 class="font-medium mt-4 mb-2">负外边距</h4>
            <div class="relative bg-purple-100 p-6 mt-6">
              <div class="bg-purple-200 p-2 text-center">父元素</div>
              <div class="mt-[-20px] ml-[20px] bg-purple-500 p-2 text-white text-center w-1/2">
                mt-[-20px] ml-[20px]
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="bg-blue-50 p-4 rounded-lg border-l-4 border-blue-500">
        <h4 class="font-medium mb-2">内外边距单位换算:</h4>
        <table class="w-full text-sm mb-4">
          <thead>
            <tr class="bg-gray-200">
              <th class="p-2 text-left">类名</th>
              <th class="p-2 text-left">rem</th>
              <th class="p-2 text-left">px</th>
            </tr>
          </thead>
          <tbody>
            <tr><td class="p-2">p-0, m-0</td><td class="p-2">0</td><td class="p-2">0px</td></tr>
            <tr><td class="p-2">p-1, m-1</td><td class="p-2">0.25rem</td><td class="p-2">4px</td></tr>
            <tr><td class="p-2">p-2, m-2</td><td class="p-2">0.5rem</td><td class="p-2">8px</td></tr>
            <tr><td class="p-2">p-4, m-4</td><td class="p-2">1rem</td><td class="p-2">16px</td></tr>
            <tr><td class="p-2">p-8, m-8</td><td class="p-2">2rem</td><td class="p-2">32px</td></tr>
          </tbody>
        </table>

        <h4 class="font-medium mb-2">代码示例:</h4>
        <pre class="bg-gray-800 text-green-300 p-3 rounded overflow-x-auto"><code>&lt;div class="p-4 m-2"&gt;四周内边距1rem，外边距0.5rem&lt;/div&gt;
&lt;div class="px-6 py-4"&gt;水平内边距1.5rem，垂直内边距1rem&lt;/div&gt;
&lt;div class="mx-auto"&gt;水平居中&lt;/div&gt;
&lt;div class="space-y-4"&gt;子元素间垂直间距1rem&lt;/div&gt;
&lt;div class="mt-[-16px]"&gt;顶部负外边距&lt;/div&gt;</code></pre>
      </div>
    </section>

    <!-- 边框 -->
    <section class="mb-12">
      <h2 class="text-2xl font-semibold mb-4 text-gray-800 border-l-4 border-blue-500 pl-3">边框 (Border)</h2>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-4">
        <div>
          <h3 class="text-xl font-medium mb-3 text-blue-700">边框宽度和颜色</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <div class="grid grid-cols-2 gap-3 mb-4">
              <div class="border p-4 text-center">border (1px)</div>
              <div class="border-2 p-4 text-center">border-2 (2px)</div>
              <div class="border-4 p-4 text-center">border-4 (4px)</div>
              <div class="border-8 p-4 text-center">border-8 (8px)</div>
            </div>

            <div class="grid grid-cols-2 gap-3">
              <div class="border-2 border-blue-500 p-4 text-center">border-blue-500</div>
              <div class="border-2 border-red-500 p-4 text-center">border-red-500</div>
              <div class="border-2 border-[#8A2BE2] p-4 text-center">border-[#8A2BE2]</div>
              <div class="border-2 border-opacity-50 border-black p-4 text-center">border-opacity-50</div>
            </div>
          </div>
        </div>

        <div>
          <h3 class="text-xl font-medium mb-3 text-blue-700">边框样式和圆角</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <div class="grid grid-cols-2 gap-3 mb-4">
              <div class="border-2 border-solid border-gray-400 p-4 text-center">border-solid</div>
              <div class="border-2 border-dashed border-gray-400 p-4 text-center">border-dashed</div>
              <div class="border-2 border-dotted border-gray-400 p-4 text-center">border-dotted</div>
              <div class="border-2 border-double border-gray-400 p-4 text-center">border-double</div>
            </div>

            <div class="grid grid-cols-2 gap-3">
              <div class="border-2 rounded-sm p-4 text-center">rounded-sm</div>
              <div class="border-2 rounded p-4 text-center">rounded</div>
              <div class="border-2 rounded-lg p-4 text-center">rounded-lg</div>
              <div class="border-2 rounded-full p-4 text-center">rounded-full</div>
              <div class="border-2 rounded-t-lg p-4 text-center">rounded-t-lg</div>
              <div class="border-2 rounded-r-lg p-4 text-center">rounded-r-lg</div>
            </div>
          </div>
        </div>
      </div>

      <div class="bg-blue-50 p-4 rounded-lg border-l-4 border-blue-500">
        <h4 class="font-medium mb-2">特定边框方向:</h4>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-3 mb-4">
          <div class="border-t-4 border-indigo-500 p-4 bg-white text-center">border-t-4</div>
          <div class="border-r-4 border-pink-500 p-4 bg-white text-center">border-r-4</div>
          <div class="border-b-4 border-amber-500 p-4 bg-white text-center">border-b-4</div>
          <div class="border-l-4 border-emerald-500 p-4 bg-white text-center">border-l-4</div>
          <div class="border-x-4 border-cyan-500 p-4 bg-white text-center">border-x-4</div>
          <div class="border-y-4 border-violet-500 p-4 bg-white text-center">border-y-4</div>
        </div>

        <h4 class="font-medium mb-2">代码示例:</h4>
        <pre class="bg-gray-800 text-green-300 p-3 rounded overflow-x-auto"><code>&lt;div class="border-2 border-blue-500 rounded-lg"&gt;带颜色的圆角边框&lt;/div&gt;
&lt;div class="border-b-2 border-gray-300"&gt;只有底部边框&lt;/div&gt;
&lt;div class="border-dashed border-2 border-red-300 rounded-full"&gt;圆形虚线边框&lt;/div&gt;
&lt;div class="border-l-8 border-green-500 pl-4"&gt;左侧粗边框，常用于引用&lt;/div&gt;</code></pre>
      </div>
    </section>

    <!-- 文本 -->
    <section class="mb-12">
      <h2 class="text-2xl font-semibold mb-4 text-gray-800 border-l-4 border-blue-500 pl-3">文本样式</h2>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-4">
        <div>
          <h3 class="text-xl font-medium mb-3 text-blue-700">字体大小和粗细</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <div class="space-y-2 mb-4">
              <p class="text-xs">text-xs (0.75rem = 12px)</p>
              <p class="text-sm">text-sm (0.875rem = 14px)</p>
              <p class="text-base">text-base (1rem = 16px)</p>
              <p class="text-lg">text-lg (1.125rem = 18px)</p>
              <p class="text-xl">text-xl (1.25rem = 20px)</p>
              <p class="text-2xl">text-2xl (1.5rem = 24px)</p>
              <p class="text-3xl">text-3xl (1.875rem = 30px)</p>
            </div>

            <div class="space-y-2">
              <p class="font-thin">font-thin (100)</p>
              <p class="font-extralight">font-extralight (200)</p>
              <p class="font-light">font-light (300)</p>
              <p class="font-normal">font-normal (400)</p>
              <p class="font-medium">font-medium (500)</p>
              <p class="font-semibold">font-semibold (600)</p>
              <p class="font-bold">font-bold (700)</p>
              <p class="font-extrabold">font-extrabold (800)</p>
              <p class="font-black">font-black (900)</p>
            </div>
          </div>
        </div>

        <div>
          <h3 class="text-xl font-medium mb-3 text-blue-700">文本对齐和变换</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <div class="space-y-3 mb-4">
              <p class="text-left border-b pb-1">text-left (左对齐)</p>
              <p class="text-center border-b pb-1">text-center (居中)</p>
              <p class="text-right border-b pb-1">text-right (右对齐)</p>
              <p class="text-justify border-b pb-1">text-justify (两端对齐) Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent libero.</p>
            </div>

            <div class="space-y-3">
              <p class="uppercase border-b pb-1">uppercase (全大写)</p>
              <p class="lowercase border-b pb-1">LOWERCASE (全小写)</p>
              <p class="capitalize border-b pb-1">capitalize each word</p>
              <p class="normal-case border-b pb-1">NORMAL-CASE</p>
              <p class="truncate w-full border-b pb-1">truncate 文本过长时截断显示省略号，这段文字会被截断...</p>
              <p class="underline">underline (下划线)</p>
              <p class="line-through">line-through (删除线)</p>
            </div>
          </div>
        </div>
      </div>

      <div class="bg-blue-50 p-4 rounded-lg border-l-4 border-blue-500">
        <h4 class="font-medium mb-2">文本间距和行高:</h4>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-4">
          <div>
            <h5 class="font-medium mb-1">字间距 (tracking)</h5>
            <p class="tracking-tight mb-1">tracking-tight (字间距较窄)</p>
            <p class="tracking-normal mb-1">tracking-normal (正常字间距)</p>
            <p class="tracking-wide mb-1">tracking-wide (字间距较宽)</p>
            <p class="tracking-wider mb-1">tracking-wider (字间距更宽)</p>
          </div>
          <div>
            <h5 class="font-medium mb-1">行高 (leading)</h5>
            <p class="leading-none mb-1">leading-none (行高为1)<br>第二行</p>
            <p class="leading-tight mb-1">leading-tight (行高较紧)<br>第二行</p>
            <p class="leading-normal mb-1">leading-normal (正常行高)<br>第二行</p>
            <p class="leading-loose mb-1">leading-loose (行高较松)<br>第二行</p>
          </div>
        </div>

        <h4 class="font-medium mb-2">文字装饰:</h4>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-3 mb-4">
          <p class="underline decoration-blue-500 underline-offset-2">蓝色下划线</p>
          <p class="underline decoration-4 decoration-wavy decoration-pink-500">波浪下划线</p>
          <p class="underline decoration-double decoration-2 decoration-emerald-500">双线下划线</p>
        </div>

        <h4 class="font-medium mb-2">代码示例:</h4>
        <pre class="bg-gray-800 text-green-300 p-3 rounded overflow-x-auto"><code>&lt;h1 class="text-3xl font-bold text-center"&gt;大标题居中&lt;/h1&gt;
&lt;p class="text-lg leading-relaxed text-gray-700"&gt;正文内容&lt;/p&gt;
&lt;p class="tracking-wide uppercase"&gt;宽间距大写文本&lt;/p&gt;
&lt;p class="truncate w-64"&gt;超长文本会被截断...&lt;/p&gt;</code></pre>
      </div>
    </section>

    <!-- 颜色梯度 -->
    <section class="mb-12">
      <h2 class="text-2xl font-semibold mb-4 text-gray-800 border-l-4 border-blue-500 pl-3">颜色梯度</h2>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-4">
        <div>
          <h3 class="text-xl font-medium mb-3 text-blue-700">文本颜色梯度</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <div class="space-y-2 mb-4">
              <h4 class="font-medium mb-1">蓝色系列:</h4>
              <p class="text-blue-50">text-blue-50 (最浅)</p>
              <p class="text-blue-100">text-blue-100</p>
              <p class="text-blue-200">text-blue-200</p>
              <p class="text-blue-300">text-blue-300</p>
              <p class="text-blue-400">text-blue-400</p>
              <p class="text-blue-500">text-blue-500</p>
              <p class="text-blue-600">text-blue-600</p>
              <p class="text-blue-700">text-blue-700</p>
              <p class="text-blue-800">text-blue-800</p>
              <p class="text-blue-900">text-blue-900 (最深)</p>
              <p class="text-blue-950">text-blue-950 (更深)</p>
            </div>

            <h4 class="font-medium mb-1">其他颜色系列:</h4>
            <div class="grid grid-cols-3 gap-2">
              <p class="text-red-500">text-red-500</p>
              <p class="text-orange-500">text-orange-500</p>
              <p class="text-amber-500">text-amber-500</p>
              <p class="text-yellow-500">text-yellow-500</p>
              <p class="text-lime-500">text-lime-500</p>
              <p class="text-green-500">text-green-500</p>
              <p class="text-emerald-500">text-emerald-500</p>
              <p class="text-teal-500">text-teal-500</p>
              <p class="text-cyan-500">text-cyan-500</p>
              <p class="text-sky-500">text-sky-500</p>
              <p class="text-indigo-500">text-indigo-500</p>
              <p class="text-violet-500">text-violet-500</p>
              <p class="text-purple-500">text-purple-500</p>
              <p class="text-fuchsia-500">text-fuchsia-500</p>
              <p class="text-pink-500">text-pink-500</p>
              <p class="text-rose-500">text-rose-500</p>
              <p class="text-gray-500">text-gray-500</p>
              <p class="text-slate-500">text-slate-500</p>
            </div>
          </div>
        </div>

        <div>
          <h3 class="text-xl font-medium mb-3 text-blue-700">背景颜色梯度</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <div class="grid grid-cols-5 gap-2 mb-4">
              <div class="h-8 bg-red-50"></div>
              <div class="h-8 bg-red-100"></div>
              <div class="h-8 bg-red-200"></div>
              <div class="h-8 bg-red-300"></div>
              <div class="h-8 bg-red-400"></div>
              <div class="h-8 bg-red-500"></div>
              <div class="h-8 bg-red-600"></div>
              <div class="h-8 bg-red-700"></div>
              <div class="h-8 bg-red-800"></div>
              <div class="h-8 bg-red-900"></div>
            </div>

            <div class="grid grid-cols-2 gap-2">
              <div class="p-3 bg-blue-100 text-center">bg-blue-100</div>
              <div class="p-3 bg-green-100 text-center">bg-green-100</div>
              <div class="p-3 bg-blue-200 text-center">bg-blue-200</div>
              <div class="p-3 bg-green-200 text-center">bg-green-200</div>
              <div class="p-3 bg-blue-300 text-center">bg-blue-300</div>
              <div class="p-3 bg-green-300 text-center">bg-green-300</div>
              <div class="p-3 bg-blue-400 text-center">bg-blue-400</div>
              <div class="p-3 bg-green-400 text-center">bg-green-400</div>
              <div class="p-3 bg-blue-500 text-white text-center">bg-blue-500</div>
              <div class="p-3 bg-green-500 text-white text-center">bg-green-500</div>
            </div>
          </div>

          <h3 class="text-xl font-medium my-3 text-blue-700">透明度</h3>
          <div class="bg-gray-100 p-4 rounded-lg">
            <div class="space-y-2">
              <div class="p-2 bg-blue-500 bg-opacity-100 text-white text-center">bg-opacity-100</div>
              <div class="p-2 bg-blue-500 bg-opacity-75 text-white text-center">bg-opacity-75</div>
              <div class="p-2 bg-blue-500 bg-opacity-50 text-white text-center">bg-opacity-50</div>
              <div class="p-2 bg-blue-500 bg-opacity-25 text-white text-center">bg-opacity-25</div>
              <div class="p-2 bg-blue-500 bg-opacity-10 text-center">bg-opacity-10</div>
            </div>
          </div>
        </div>
      </div>

      <div class="bg-blue-50 p-4 rounded-lg border-l-4 border-blue-500">
        <h4 class="font-medium mb-2">渐变背景:</h4>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-4">
          <div class="h-24 bg-gradient-to-r from-cyan-500 to-blue-500 rounded-lg flex items-center justify-center text-white">
            bg-gradient-to-r from-cyan-500 to-blue-500
          </div>
          <div class="h-24 bg-gradient-to-tr from-pink-500 via-purple-500 to-indigo-500 rounded-lg flex items-center justify-center text-white">
            带via中间色的三色渐变
          </div>
        </div>

        <h4 class="font-medium mb-2">自定义颜色:</h4>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-3 mb-4">
          <div class="p-3 bg-[#8A2BE2] text-white text-center rounded">bg-[#8A2BE2]</div>
          <div class="p-3 bg-[rgb(64,224,208)] text-center rounded">bg-[rgb(64,224,208)]</div>
          <div class="p-3 bg-[hsl(335,100%,50%)] text-white text-center rounded">bg-[hsl(335,100%,50%)]</div>
        </div>

        <h4 class="font-medium mb-2">代码示例:</h4>
        <pre class="bg-gray-800 text-green-300 p-3 rounded overflow-x-auto"><code>&lt;div class="text-blue-600 hover:text-blue-800"&gt;悬停时颜色变深&lt;/div&gt;
&lt;div class="bg-gradient-to-r from-purple-500 to-pink-500"&gt;渐变背景&lt;/div&gt;
&lt;div class="bg-opacity-50 bg-black text-white"&gt;半透明背景&lt;/div&gt;
&lt;div class="bg-[#ff5733] text-[#ffffff]"&gt;自定义颜色&lt;/div&gt;</code></pre>
      </div>
    </section>

    <div class="text-center text-gray-500 mt-12 mb-6">
      <p>Tailwind CSS 提供了丰富的工具类，使我们能够快速构建现代化的用户界面。</p>
      <p class="mt-2">查看 <a href="https://tailwindcss.com/docs" target="_blank" class="text-blue-600 hover:underline">官方文档</a> 了解更多详细信息。</p>
    </div>
  </div>
</template>

<script setup lang="ts">
// 组件逻辑
</script>

<style scoped>
/* Tailwind 已提供所有所需样式 */
</style>
