<template>
  <div class="w-full border-b border-gray-200 shadow-sm bg-white">
    <div class="container mx-auto flex md:flex-row flex-row-reverse justify-between items-center p-4">
      <h1 class="text-3xl font-extrabold text-amber-600 tracking-tight">Furnitures</h1>

      <!-- Desktop Menu -->
      <ul class="hidden md:flex space-x-6 font-semibold text-gray-700">
          <Menu><></Menu>
      </ul>

      <!-- Icon Area -->
      <div class="hidden md:flex space-x-4 text-amber-600">
        <a href="#" class="hover:text-amber-700 transition-transform duration-200 hover:scale-110" style="font-size: 1.5rem">
          <span class="pi pi-shopping-bag"></span>
        </a>
        <a href="#" class="hover:text-amber-700 transition-transform duration-200 hover:scale-110" style="font-size: 1.5rem">
          <span class="pi pi-user"></span>
        </a>
      </div>

      <!-- Hamburger Button -->
      <div class="md:hidden flex items-center">
        <button @click="toggleMenu" class="text-gray-700 focus:outline-none hover:text-amber-600 transition-colors duration-200">
          <transition name="fade-rotate" mode="out-in">
            <svg
              v-if="!isOpen"
              key="menu"
              class="w-7 h-7"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              viewBox="0 0 24 24"
              stroke-linecap="round"
              stroke-linejoin="round"
            >
              <path d="M4 6h16M4 12h16M4 18h16" />
            </svg>
            <svg
              v-else
              key="close"
              class="w-7 h-7"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              viewBox="0 0 24 24"
              stroke-linecap="round"
              stroke-linejoin="round"
            >
              <path d="M6 18L18 6M6 6l12 12" />
            </svg>
          </transition>
        </button>
      </div>
    </div>

    <!-- Mobile Menu -->
    <transition name="slide-fade">
      <div
        v-show="isOpen"
        class="md:hidden px-4 pb-4 space-y-4"
      >
        <ul class="flex flex-col space-y-2 font-semibold text-gray-700">
          <Menu><></Menu>
        </ul>

        <div class="flex w-full bg-amber-600 items-center justify-center divide-x divide-gray-700 rounded-xl overflow-hidden shadow-md">
          <a href="#" class="w-1/2 flex items-center justify-center py-3 text-white hover:bg-amber-700 transition duration-300 ease-in-out" style="font-size: 1.5rem">
            <span class="pi pi-shopping-bag"></span>
          </a>
          <a href="#" class="w-1/2 flex items-center justify-center py-3 text-white hover:bg-amber-700 transition duration-300 ease-in-out" style="font-size: 1.5rem">
            <span class="pi pi-user"></span>
          </a>
        </div>
      </div>
    </transition>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { Menu } from '@/components/atom'

const isOpen = ref(false)
function toggleMenu() {
  isOpen.value = !isOpen.value
}
</script>

<style scoped>
/* Transisi untuk hamburger icon */
.fade-rotate-enter-active,
.fade-rotate-leave-active {
  transition: all 0.3s ease;
}
.fade-rotate-enter-from,
.fade-rotate-leave-to {
  opacity: 0;
  transform: rotate(-90deg) scale(0.95);
}
.fade-rotate-enter-to,
.fade-rotate-leave-from {
  opacity: 1;
  transform: rotate(0deg) scale(1);
}

/* Transisi menu mobile */
.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: all 0.3s ease;
}
.slide-fade-enter-from,
.slide-fade-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
.slide-fade-enter-to,
.slide-fade-leave-from {
  opacity: 1;
  transform: translateY(0);
}
</style>
