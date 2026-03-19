<script setup>
import { ref, defineAsyncComponent } from 'vue'

const templates = [
  { id: 'dashboard', label: 'Dashboard', component: defineAsyncComponent(() => import('./templates/dashboard.vue')) },
  { id: 'form-page', label: 'Form Page', component: defineAsyncComponent(() => import('./templates/form-page.vue')) },
  { id: 'landing-page', label: 'Landing Page', component: defineAsyncComponent(() => import('./templates/landing-page.vue')) },
  { id: 'list-detail', label: 'List & Detail', component: defineAsyncComponent(() => import('./templates/list-detail.vue')) },
  { id: 'onboarding-wizard', label: 'Onboarding Wizard', component: defineAsyncComponent(() => import('./templates/onboarding-wizard.vue')) },
  { id: 'settings-page', label: 'Settings Page', component: defineAsyncComponent(() => import('./templates/settings-page.vue')) },
]

const active = ref(templates[0].id)
const current = () => templates.find(t => t.id === active.value)
</script>

<template>
  <div class="flex flex-col h-screen bg-white">
    <!-- Tab bar -->
    <div class="flex items-center gap-1 px-4 py-2 border-b border-gray-200 bg-gray-50 shrink-0 overflow-x-auto">
      <button
        v-for="t in templates"
        :key="t.id"
        @click="active = t.id"
        :class="[
          'px-4 py-1.5 rounded text-sm font-medium whitespace-nowrap transition-colors',
          active === t.id
            ? 'bg-gray-900 text-white'
            : 'text-gray-600 hover:bg-gray-200'
        ]"
      >
        {{ t.label }}
      </button>
    </div>

    <!-- Template view -->
    <div class="flex-1 overflow-auto">
      <Suspense>
        <component :is="current().component" />
        <template #fallback>
          <div class="flex items-center justify-center h-full text-gray-400 text-sm">Loading...</div>
        </template>
      </Suspense>
    </div>
  </div>
</template>
