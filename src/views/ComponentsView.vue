<script setup>
import ComponentObject from '@/components/ComponentObject.vue'
import ComponentSection from '@/components/ComponentSection.vue'
import { ref, onMounted } from 'vue'
import componentsData from '@/data/components.json'

const isVisible = ref(false)

onMounted(() => {
  requestAnimationFrame(() => {
    isVisible.value = true
  })
})
</script>

<template>
  <div class="min-h-screen grid grid-cols-1 lg:grid-cols-[250px_1fr]">
    <!-- Sidebar -->
    <aside class="hidden lg:block bg-gray-50 border-r border-gray-200 p-4 h-full">
      <nav class="space-y-2 mt-20 fixed">
        <!-- Navigation items -->
        <h2 class="text-body font-semibold">COMPONENTS</h2>
        <div class="flex flex-col gap-1.5 mt-4">
          <router-link
            v-for="section in componentsData"
            :key="section.id"
            class="text-small hover:opacity-70 transition-all hover:pl-1"
            :to="`/components#${section.id}`"
            >{{ section.name }}</router-link>
        </div>
      </nav>
    </aside>

    <!-- Main content area -->
    <main
      class="p-6 overflow-auto mt-20 transition-all"
      :class="isVisible ? 'opacity-100 translate-y-0' : 'opacity-0 translate-y-6'"
    >
      <!-- Dashboard content -->

      <component-section
        v-for="section in componentsData"
        :key="section.id"
        :id="section.id"
        :name="section.name"
        :description="section.description"
      >
        <component-object
          v-for="component in section.components"
          :key="component.name"
          :name="component.name"
          :code="component.code"
        ></component-object>
      </component-section>
    </main>
  </div>
</template>
