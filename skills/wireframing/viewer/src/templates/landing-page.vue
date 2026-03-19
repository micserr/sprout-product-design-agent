<script setup>
import { Card, CardContent } from '@/components/ui/card'
import { Button } from '@/components/ui/button'
import { Input } from '@/components/ui/input'
import { Separator } from '@/components/ui/separator'

const navLinks = ['FEATURES', 'PRICING', 'ABOUT', 'BLOG']
const features = [
  { title: 'FEATURE ONE', description: 'Description of the first key feature and what value it provides to users.' },
  { title: 'FEATURE TWO', description: 'Description of the second key feature and what value it provides to users.' },
  { title: 'FEATURE THREE', description: 'Description of the third key feature and what value it provides to users.' },
]
const testimonials = [
  { quote: '"TESTIMONIAL QUOTE PLACEHOLDER. This is what a satisfied user said about the product."', author: 'USER NAME', role: 'ROLE, COMPANY' },
  { quote: '"TESTIMONIAL QUOTE PLACEHOLDER. Another satisfied user sharing their experience with the product."', author: 'USER NAME', role: 'ROLE, COMPANY' },
  { quote: '"TESTIMONIAL QUOTE PLACEHOLDER. A third user endorsing the product with their positive review."', author: 'USER NAME', role: 'ROLE, COMPANY' },
]
const footerCols = [
  { heading: 'PRODUCT', links: ['FEATURES', 'PRICING', 'CHANGELOG', 'ROADMAP'] },
  { heading: 'COMPANY', links: ['ABOUT', 'BLOG', 'CAREERS', 'PRESS'] },
  { heading: 'RESOURCES', links: ['DOCS', 'API', 'GUIDES', 'SUPPORT'] },
  { heading: 'LEGAL', links: ['PRIVACY', 'TERMS', 'COOKIES', 'SECURITY'] },
]
</script>

<template>
  <div class="min-h-screen bg-white">

    <!-- STICKY NAV -->
    <nav class="sticky top-0 z-10 h-16 bg-white border-b border-gray-200 flex items-center justify-between px-8">
      <div class="flex items-center gap-8">
        <div class="w-24 h-6 bg-gray-300 rounded text-xs text-gray-500 flex items-center justify-center">LOGO</div>
        <div class="hidden md:flex items-center gap-6">
          <a v-for="link in navLinks" :key="link" href="#" class="text-sm text-gray-500 hover:text-gray-900">{{ link }}</a>
        </div>
      </div>
      <div class="flex items-center gap-3">
        <Button variant="ghost" class="text-sm text-gray-600">LOG IN</Button>
        <Button class="text-sm">GET STARTED</Button>
      </div>
    </nav>

    <!-- HERO -->
    <section class="bg-gray-50 py-20 px-8 text-center">
      <div class="max-w-3xl mx-auto space-y-6">
        <span class="inline-block px-3 py-1 bg-gray-200 rounded-full text-xs text-gray-600 font-medium">ANNOUNCEMENT BADGE PLACEHOLDER</span>
        <h1 class="text-5xl font-bold text-gray-900 leading-tight">MAIN HEADLINE<br>GOES HERE</h1>
        <p class="text-lg text-gray-500">Subheadline describing the product value proposition in one to two sentences maximum.</p>
        <div class="flex items-center justify-center gap-4">
          <Button class="px-6">PRIMARY CTA</Button>
          <Button variant="outline" class="px-6">SECONDARY CTA</Button>
        </div>
        <!-- Hero image placeholder -->
        <div class="mt-8 h-64 border-2 border-dashed border-gray-300 rounded-lg flex items-center justify-center bg-white">
          <span class="text-sm text-gray-400">HERO IMAGE / SCREENSHOT PLACEHOLDER</span>
        </div>
      </div>
    </section>

    <!-- FEATURES -->
    <section class="py-16 px-8">
      <div class="max-w-5xl mx-auto">
        <div class="text-center mb-12">
          <h2 class="text-3xl font-bold text-gray-900">KEY FEATURES HEADING</h2>
          <p class="text-gray-500 mt-3">Supporting description for the features section.</p>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <Card v-for="feature in features" :key="feature.title">
            <CardContent class="pt-6 space-y-3">
              <div class="w-10 h-10 bg-gray-200 rounded flex items-center justify-center">
                <div class="w-5 h-5 bg-gray-400 rounded-sm" />
              </div>
              <h3 class="font-semibold text-gray-900">{{ feature.title }}</h3>
              <p class="text-sm text-gray-500">{{ feature.description }}</p>
            </CardContent>
          </Card>
        </div>
      </div>
    </section>

    <Separator />

    <!-- TESTIMONIALS -->
    <section class="py-16 px-8 bg-gray-50">
      <div class="max-w-5xl mx-auto">
        <div class="text-center mb-12">
          <h2 class="text-3xl font-bold text-gray-900">SOCIAL PROOF HEADING</h2>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          <Card v-for="testimonial in testimonials" :key="testimonial.author">
            <CardContent class="pt-6 space-y-4">
              <!-- Star rating placeholder -->
              <div class="flex gap-1">
                <div v-for="i in 5" :key="i" class="w-4 h-4 bg-gray-300 rounded-sm" />
              </div>
              <p class="text-sm text-gray-600 italic">{{ testimonial.quote }}</p>
              <div class="flex items-center gap-3">
                <div class="w-8 h-8 rounded-full bg-gray-300 shrink-0" />
                <div>
                  <p class="text-sm font-medium text-gray-800">{{ testimonial.author }}</p>
                  <p class="text-xs text-gray-400">{{ testimonial.role }}</p>
                </div>
              </div>
            </CardContent>
          </Card>
        </div>
      </div>
    </section>

    <!-- CTA BANNER -->
    <section class="bg-gray-800 py-16 px-8 text-center">
      <div class="max-w-xl mx-auto space-y-4">
        <h2 class="text-3xl font-bold text-white">CTA BANNER HEADLINE</h2>
        <p class="text-gray-300">Supporting description for the call-to-action section.</p>
        <div class="flex gap-3 max-w-sm mx-auto mt-6">
          <Input placeholder="YOUR EMAIL ADDRESS" class="bg-white" />
          <Button variant="outline" class="shrink-0 bg-white text-gray-800 hover:bg-gray-100">GET STARTED</Button>
        </div>
      </div>
    </section>

    <!-- FOOTER -->
    <footer class="bg-gray-100 py-12 px-8">
      <div class="max-w-5xl mx-auto">
        <div class="grid grid-cols-2 md:grid-cols-4 gap-8 mb-8">
          <div v-for="col in footerCols" :key="col.heading">
            <p class="text-xs font-bold tracking-widest text-gray-500 mb-3">{{ col.heading }}</p>
            <ul class="space-y-2">
              <li v-for="link in col.links" :key="link">
                <a href="#" class="text-sm text-gray-500 hover:text-gray-800">{{ link }}</a>
              </li>
            </ul>
          </div>
        </div>
        <Separator class="mb-6" />
        <div class="flex items-center justify-between">
          <div class="w-20 h-5 bg-gray-300 rounded text-xs flex items-center justify-center text-gray-500">LOGO</div>
          <p class="text-xs text-gray-400">© 2024 COMPANY NAME. All rights reserved.</p>
        </div>
      </div>
    </footer>

  </div>
</template>
