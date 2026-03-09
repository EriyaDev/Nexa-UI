<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'
// import { useDarkMode } from '@/composables/useDarkMode'

// const { isDark, toggleDark } = useDarkMode()

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
  <div
    class="header bg-primary w-full py-4 fixed top-0 left-0 z-50 border-b border-b-text-secondary/10"
  >
    <nav class="container mx-auto flex flex-row items-center justify-between px-3">
      <RouterLink to="/" class="text-xl font-bold font-grotesk"
        ><span class="text-avocado-600">Nexa</span> UI</RouterLink
      >

      <ul class="hidden md:flex flex-row items-center space-x-4">
        <li><RouterLink class="navbar-link" to="/">Home</RouterLink></li>
        <li><RouterLink class="navbar-link" to="/components">Components</RouterLink></li>
        <li><RouterLink class="navbar-link" to="/docs">Documentation</RouterLink></li>
        <li>
          <a class="navbar-link" href="https://github.com/EriyaDev/Nexa-UI"
            ><i class="ri-github-fill text-xl"></i
          ></a>
        </li>
        <!-- <li>
          <button
            id="dark-mode-toggle"
            @click="toggleDark"
            :aria-label="isDark ? 'Switch to light mode' : 'Switch to dark mode'"
            class="theme-toggle-btn"
          >
            <span class="theme-toggle-icon" :class="{ 'is-dark': isDark }">
              <i class="ri-sun-line sun-icon"></i>
              <i class="ri-moon-line moon-icon"></i>
            </span>
          </button>
        </li> -->
      </ul>

      <div class="relative md:hidden">
        <button class="md:hidden" v-on:click="toggleMenu">
          <i class="ri-menu-line text-2xl"></i>
        </button>

        <div
          class="absolute top-10 right-10 bg-primary border border-text-primary/10 p-5 rounded-md"
          v-if="isMenuOpen"
        >
          <ul class="flex flex-col items-end space-y-2">
            <li><RouterLink class="navbar-link" to="/">Home</RouterLink></li>
            <li><RouterLink class="navbar-link" to="/components">Components</RouterLink></li>
            <li><RouterLink class="navbar-link" to="/docs">Documentation</RouterLink></li>
            <li>
              <a class="navbar-link" href="https://github.com/EriyaDev/Nexa-UI"
                ><i class="ri-github-fill text-xl"></i>
              </a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </div>
  <RouterView v-slot="{ Component }">
    <Transition name="page" mode="out-in">
      <component :is="Component" />
    </Transition>
  </RouterView>

  <div
    class="flex flex-row items-center justify-center py-10 border-t border-b border-text-primary/10"
  >
    <p class="text-body opacity-55">
      Made with ❤️ by <a class="link" href="https://github.com/EriyaDev">Elijah Emmanuel</a>
    </p>
  </div>
</template>

<style>
.page-enter-active,
.page-leave-active {
  transition:
    opacity 0.3s ease,
    transform 0.3s ease;
}
.page-enter-from {
  opacity: 0;
  transform: translateY(12px);
}
.page-leave-to {
  opacity: 0;
  transform: translateY(-8px);
}
</style>
