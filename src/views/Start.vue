<template>
    <div class="my-5">
        <div v-for="(item, i) in title" class="mt-5" :key="i">
            <h1 class="text-[20px] font-bold px-3 mx-2 border-l-8">{{ item }}</h1>
            <CodeBlock language="javascript" :code='code[i]' />
        </div>
        <div class="mt-8 mx-2">
            <div class="bg-amber-50 border-l-4 border-amber-500 p-4 rounded-r-md shadow-sm">
                <div class="flex items-center mb-2">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-amber-500 mr-2" fill="none"
                        viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                            d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z" />
                    </svg>
                    <h3 class="font-bold text-amber-800">注意事项</h3>
                </div>
                <p class="text-amber-700 pl-8">
                    在 Tailwind CSS 4.0 中，如果你提供了全局重置样式 <code
                        class="bg-amber-100 px-1 rounded font-mono">* { padding: 0; margin: 0; }</code> 会与 Tailwind
                    的默认样式冲突，导致内边距和外边距工具类失效。这是因为
                    Tailwind 4.0 默认启用了<code class="bg-amber-100 px-1 rounded font-mono">preflight</code>
                    功能，它会自动重置所有元素的内外边距。
                </p>
            </div>
        </div> 
        <div class="mt-5">
            <h1 class="text-[20px] font-bold px-3 mx-2 border-l-8">4、Visual Studio Code 安装官方提示插件</h1>
            <CodeBlock language="插件名" code='Tailwind Css IntelliSense' />
            <div class="text-gray-900 text-[16px] mt-2 mx-2">vscode直接搜索插件，安装插件后写tailwindcss就会有代码提示，根本不需要记完整代码，只需记住关键词即可。
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import CodeBlock from '@/components/CodeBlock.vue'
const title = [
    '1、安装依赖',
    '2、配置 Vite 插件 (vite.config.ts)',
    '3、导入 Tailwind CSS (style.css，全局的css处导入皆可)'
]
const str1 = `npm install tailwindcss @tailwindcss/vite`;
const str2 = `    import { defineConfig } from 'vite'
    import tailwindcss from '@tailwindcss/vite'
    export default defineConfig({
    plugins: [
       tailwindcss(),
    ],
    })
`;
const str3 = `@import "tailwindcss";`;
const code = [str1, str2, str3];
</script>

<style scoped></style>