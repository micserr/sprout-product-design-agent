<script setup>
import { ref } from 'vue'
import { Card, CardContent, CardHeader } from '@/components/ui/card'
import { Button } from '@/components/ui/button'
import { Badge } from '@/components/ui/badge'
import { Input } from '@/components/ui/input'

const selectedIndex = ref(0)

const items = [
  { title: 'ITEM TITLE ONE', subtitle: 'CATEGORY · SUBCATEGORY', time: '2 min ago', preview: 'Short preview of the item content. This shows the first two lines of the description before it is cut off.' },
  { title: 'ITEM TITLE TWO', subtitle: 'CATEGORY · SUBCATEGORY', time: '1 hr ago', preview: 'Short preview of the item content. This shows the first two lines of the description before it is cut off.' },
  { title: 'ITEM TITLE THREE', subtitle: 'CATEGORY · SUBCATEGORY', time: '3 hr ago', preview: 'Short preview of the item content. This shows the first two lines of the description before it is cut off.' },
  { title: 'ITEM TITLE FOUR', subtitle: 'CATEGORY · SUBCATEGORY', time: 'Yesterday', preview: 'Short preview of the item content. This shows the first two lines of the description before it is cut off.' },
  { title: 'ITEM TITLE FIVE', subtitle: 'CATEGORY · SUBCATEGORY', time: '2 days ago', preview: 'Short preview of the item content. This shows the first two lines of the description before it is cut off.' },
  { title: 'ITEM TITLE SIX', subtitle: 'CATEGORY · SUBCATEGORY', time: '3 days ago', preview: 'Short preview of the item content. This shows the first two lines of the description before it is cut off.' },
]

const fields = [
  { label: 'FIELD LABEL', value: 'FIELD VALUE' },
  { label: 'FIELD LABEL', value: 'FIELD VALUE' },
  { label: 'FIELD LABEL', value: 'FIELD VALUE' },
  { label: 'FIELD LABEL', value: 'FIELD VALUE' },
]
</script>

<template>
  <div class="flex flex-col h-screen bg-gray-50">
    <!-- TOP NAV -->
    <nav class="h-14 bg-gray-900 flex items-center justify-between px-6 shrink-0">
      <div class="w-24 h-6 bg-gray-600 rounded text-xs text-gray-400 flex items-center justify-center">LOGO</div>
      <div class="flex items-center gap-3">
        <Button variant="ghost" class="text-gray-300 text-sm h-8">+ NEW ITEM</Button>
        <div class="w-8 h-8 rounded-full bg-gray-600 flex items-center justify-center text-xs text-gray-300">U</div>
      </div>
    </nav>

    <div class="flex flex-1 overflow-hidden">
      <!-- LIST PANEL -->
      <div class="w-2/5 flex flex-col border-r border-gray-200 bg-white">
        <!-- Search / Filter -->
        <div class="p-3 border-b border-gray-200 flex gap-2">
          <Input placeholder="SEARCH..." class="h-8 text-xs" />
          <Button variant="outline" class="h-8 text-xs shrink-0">FILTER</Button>
        </div>

        <div class="px-4 py-2 border-b border-gray-100">
          <p class="text-xs text-gray-400">{{ items.length }} ITEMS</p>
        </div>

        <!-- List Items -->
        <div class="flex-1 overflow-y-auto divide-y divide-gray-100">
          <button
            v-for="(item, i) in items"
            :key="i"
            class="w-full text-left px-4 py-3 flex gap-3 transition-colors"
            :class="i === selectedIndex ? 'bg-gray-100 border-l-4 border-gray-800' : 'border-l-4 border-transparent hover:bg-gray-50'"
            @click="selectedIndex = i"
          >
            <div class="w-8 h-8 rounded bg-gray-200 shrink-0 mt-0.5" />
            <div class="min-w-0 flex-1">
              <div class="flex justify-between items-start">
                <p class="text-sm font-medium text-gray-900 truncate">{{ item.title }}</p>
                <p class="text-xs text-gray-400 shrink-0 ml-2">{{ item.time }}</p>
              </div>
              <p class="text-xs text-gray-500 mt-0.5">{{ item.subtitle }}</p>
              <p class="text-xs text-gray-400 mt-1 line-clamp-2">{{ item.preview }}</p>
            </div>
          </button>
        </div>
      </div>

      <!-- DETAIL PANEL -->
      <div class="flex-1 overflow-y-auto p-6 space-y-4">
        <!-- Header -->
        <div class="flex items-start justify-between">
          <div>
            <h1 class="text-xl font-semibold text-gray-900">{{ items[selectedIndex].title }}</h1>
            <p class="text-sm text-gray-400 mt-1">
              METADATA · {{ items[selectedIndex].subtitle }} · {{ items[selectedIndex].time }}
            </p>
          </div>
          <div class="flex gap-2">
            <Button variant="outline" class="text-xs h-8">SECONDARY ACTION</Button>
            <Button class="text-xs h-8">PRIMARY ACTION</Button>
          </div>
        </div>

        <Badge variant="outline" class="text-xs text-gray-600 border-gray-300">STATUS BADGE</Badge>

        <!-- Main content -->
        <Card>
          <CardHeader class="pb-2">
            <p class="text-xs font-bold tracking-widest text-gray-400">DETAIL CONTENT</p>
          </CardHeader>
          <CardContent class="space-y-2">
            <div class="h-4 bg-gray-200 rounded w-full" />
            <div class="h-4 bg-gray-100 rounded w-5/6" />
            <div class="h-4 bg-gray-200 rounded w-full" />
            <div class="h-4 bg-gray-100 rounded w-4/5" />
            <div class="h-4 bg-gray-200 rounded w-3/4" />
          </CardContent>
        </Card>

        <!-- Additional fields -->
        <Card>
          <CardHeader class="pb-2">
            <p class="text-xs font-bold tracking-widest text-gray-400">ADDITIONAL INFORMATION</p>
          </CardHeader>
          <CardContent>
            <div class="grid grid-cols-2 gap-4">
              <div v-for="field in fields" :key="field.label">
                <p class="text-xs font-medium text-gray-400">{{ field.label }}</p>
                <p class="text-sm text-gray-700 mt-0.5">{{ field.value }}</p>
              </div>
            </div>
          </CardContent>
        </Card>
      </div>
    </div>
  </div>
</template>
