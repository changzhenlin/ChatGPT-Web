<script setup lang='ts'>
import { defineAsyncComponent, ref } from 'vue'
import { HoverButton, UserAvatar } from '@/components/common'

const Setting = defineAsyncComponent(() => import('@/components/common/Setting/index.vue'))
const Prompt = defineAsyncComponent(() => import('@/components/common/Prompt/index.vue'))

const show = ref(false)
const shows = ref(false)
</script>

<template>
  <footer class="flex items-center justify-between min-w-0 p-4 overflow-hidden border-t dark:border-neutral-800">
    <div class="flex-1 flex-shrink-0 overflow-hidden">
      <UserAvatar />
    </div>

    <HoverButton @click="shows = true">
      <span class="text-xl text-[#4f555e] dark:text-white">
        Pro
      </span>
    </HoverButton>

    <Setting v-if="show" v-model:visible="show" />
    <Prompt v-if="shows" v-model:visible="shows" />
  </footer>
</template>
