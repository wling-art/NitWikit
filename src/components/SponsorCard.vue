<script setup lang="ts">
const props = defineProps<{
    items: {
        name: string;
        amount: number;
        qid: string;
    }[];
}>();
</script>

<template>
    <div class="not-content grid grid-cols-2 sm:grid-cols-4 md:grid-cols-5 lg:grid-cols-6 gap-3">
        <div 
            v-for="item in props.items" 
            :key="item.qid" 
            class="group flex flex-col items-center p-3 bg-base-100 rounded-lg border border-base-200 transition-all duration-300 hover:shadow-lg hover:-translate-y-1 hover:border-(--sl-color-accent)/50 hover:bg-(--sl-color-accent)/5"
        >
            <div class="daisy-avatar mb-3">
                <div class="w-16 rounded-lg ring ring-base-200 ring-offset-2 ring-offset-base-100 transition-all duration-300 group-hover:ring-(--sl-color-accent)">
                    <img :src="`https://q.qlogo.cn/g?b=qq&nk=${item.qid}&s=100`" :alt="item.name" loading="lazy" />
                </div>
            </div>
            <div class="text-center w-full">
                <h3 class="font-bold text-base truncate px-1 group-hover:text-(--sl-color-accent) transition-colors">{{ item.name }}</h3>
                <div class="daisy-badge daisy-badge-ghost daisy-badge-sm mt-2 font-mono text-(--sl-color-accent) bg-(--sl-color-accent)/10">
                    ¥{{ item.amount }}
                </div>
            </div>
        </div>
    </div>
</template>