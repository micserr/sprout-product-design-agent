<script setup>
import { ref, computed } from 'vue'
import { Card, CardContent, CardHeader, CardFooter } from '@/components/ui/card'
import { Button } from '@/components/ui/button'
import { Input } from '@/components/ui/input'
import { Label } from '@/components/ui/label'

const currentStep = ref(1)
const totalSteps = 4

const steps = [
  { label: 'STEP 1', title: 'WELCOME', description: 'Tell us a bit about yourself to get started.' },
  { label: 'STEP 2', title: 'YOUR ACCOUNT', description: 'Set up your account preferences and settings.' },
  { label: 'STEP 3', title: 'CONFIGURE', description: 'Configure your workspace to fit your workflow.' },
  { label: 'STEP 4', title: 'FINISH', description: "You're all set. Review your setup before completing." },
]

const activeStep = computed(() => steps[currentStep.value - 1])
</script>

<template>
  <div class="flex flex-col min-h-screen bg-gray-50">
    <!-- LOGO HEADER -->
    <header class="h-14 bg-white border-b border-gray-200 flex items-center justify-center">
      <div class="w-24 h-6 bg-gray-300 rounded text-xs text-gray-500 flex items-center justify-center">LOGO</div>
    </header>

    <main class="flex-1 flex items-center justify-center p-6">
      <div class="w-full max-w-lg space-y-6">

        <!-- STEP INDICATOR -->
        <div class="flex items-center">
          <template v-for="(step, i) in steps" :key="i">
            <div class="flex flex-col items-center">
              <div
                class="w-9 h-9 rounded-full flex items-center justify-center text-sm font-semibold transition-all"
                :class="i + 1 <= currentStep
                  ? 'bg-gray-800 text-white'
                  : 'border-2 border-gray-300 bg-white text-gray-400'"
              >
                {{ i + 1 }}
              </div>
              <p class="text-xs text-gray-400 mt-1 hidden sm:block">{{ step.label }}</p>
            </div>
            <div
              v-if="i < steps.length - 1"
              class="flex-1 h-0.5 mx-2 transition-all"
              :class="i + 1 < currentStep ? 'bg-gray-800' : 'bg-gray-300'"
            />
          </template>
        </div>

        <!-- STEP CARD -->
        <Card>
          <CardHeader>
            <p class="text-xs font-bold tracking-widest text-gray-400">STEP {{ currentStep }} OF {{ totalSteps }}</p>
            <h2 class="text-lg font-semibold text-gray-900 mt-1">{{ activeStep.title }}</h2>
            <p class="text-sm text-gray-400">{{ activeStep.description }}</p>
          </CardHeader>

          <CardContent class="space-y-4">
            <div class="space-y-1.5">
              <Label class="text-sm text-gray-700">FIELD LABEL ONE</Label>
              <Input placeholder="PLACEHOLDER TEXT" />
              <p class="text-xs text-gray-400">Helper text for this field.</p>
            </div>
            <div class="space-y-1.5">
              <Label class="text-sm text-gray-700">FIELD LABEL TWO</Label>
              <Input placeholder="PLACEHOLDER TEXT" />
            </div>
          </CardContent>

          <CardFooter class="flex items-center justify-between">
            <Button
              variant="outline"
              :disabled="currentStep === 1"
              :class="currentStep === 1 ? 'cursor-not-allowed opacity-40' : ''"
              @click="currentStep > 1 && currentStep--"
            >
              Back
            </Button>
            <p class="text-xs text-gray-400">Step {{ currentStep }} of {{ totalSteps }}</p>
            <Button @click="currentStep < totalSteps && currentStep++">
              {{ currentStep === totalSteps ? 'Finish' : 'Continue' }}
            </Button>
          </CardFooter>
        </Card>

        <!-- Skip link -->
        <p class="text-center text-xs text-gray-400">
          <a href="#" class="underline hover:text-gray-600">Skip setup for now</a>
        </p>

      </div>
    </main>
  </div>
</template>
