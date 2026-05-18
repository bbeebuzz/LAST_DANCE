<script setup lang="ts">
import { ref, onMounted } from "vue";

// ==========================================
// 1. Theme Management (Dark/Light Mode)
// ==========================================
const isDark = ref(false);

function applyTheme(value: boolean) {
  isDark.value = value;
  document.documentElement.classList.toggle("dark", value);
  localStorage.setItem("color-theme", value ? "dark" : "light");
}

onMounted(() => {
  const savedTheme = localStorage.getItem("color-theme");
  const shouldUseDark =
    savedTheme === "dark" ||
    (savedTheme === null &&
      window.matchMedia("(prefers-color-scheme: dark)").matches);
  applyTheme(shouldUseDark);
});

function toggleTheme() {
  applyTheme(!isDark.value);
}

// ==========================================
// 2. Dropdown State
// ==========================================
const isDropdownOpen = ref(false);

function toggleDropdown() {
  isDropdownOpen.value = !isDropdownOpen.value;
}
</script>

<template>
  <div class=" bg-slate-50 dark:bg-slate-900 transition-colors duration-300 font-sans">
    
    <header class="sticky top-0 z-30 border-b border-slate-200 dark:border-slate-800 bg-white/90 dark:bg-slate-900/90 backdrop-blur w-full">
      <nav class="mx-auto max-w-7xl flex items-center justify-between px-6 py-4 gap-5 w-full">
        
        <a href="#" class="flex items-center gap-3">
          <div class="flex items-center justify-center h-10 w-10 rounded-2xl bg-indigo-600 text-sm font-bold text-white shadow-sm">
            LS
          </div>
          <div>
            <h1 class="text-lg font-bold text-gray-900 dark:text-white">LearnSpace</h1>
            <p class="text-sm text-gray-500 dark:text-gray-400">Your learning companion</p>
          </div>
        </a>

        <ul class="text-lg font-medium text-gray-700 dark:text-gray-300 hidden md:flex">
          <li class="flex justify-center items-center gap-8">
            <a href="#" class="transition hover:text-indigo-600 dark:hover:text-indigo-400">Dashboard</a>
            <a href="#" class="transition hover:text-indigo-600 dark:hover:text-indigo-400">Courses</a>
            <a href="#" class="transition hover:text-indigo-600 dark:hover:text-indigo-400">Assignments</a>
            <a href="#" class="transition hover:text-indigo-600 dark:hover:text-indigo-400">Progress</a>
          </li>
        </ul>

        <div class="flex items-center gap-5">
          
          <div class="relative">
            <div v-if="isDropdownOpen" @click="isDropdownOpen = false" class="fixed inset-0 z-40"></div>

            <div
              @click="toggleDropdown"
              class="relative z-50 flex gap-3 items-center justify-center border border-gray-300 dark:border-slate-700 rounded-3xl px-5 py-2 hover:bg-gray-50 dark:hover:bg-slate-800 transition cursor-pointer select-none"
            >
              <div class="w-10 h-10 rounded-full bg-indigo-100 dark:bg-indigo-500/20 text-indigo-600 dark:text-indigo-300 flex items-center justify-center font-bold text-l">
                ST
              </div>
              <div class="flex justify-center items-center text-lg font-medium text-gray-900 dark:text-white">
                Student
              </div>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-4 h-4 text-gray-800 dark:text-gray-300 transition-transform duration-200"
                :class="{ 'rotate-180': isDropdownOpen }"
                fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="4"
              >
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7" />
              </svg>
            </div>

            <transition 
              enter-active-class="transition ease-out duration-100" 
              enter-from-class="transform opacity-0 scale-95" 
              enter-to-class="transform opacity-100 scale-100" 
              leave-active-class="transition ease-in duration-75" 
              leave-from-class="transform opacity-100 scale-100" 
              leave-to-class="transform opacity-0 scale-95"
            >
              <div 
                v-show="isDropdownOpen"
                class="absolute right-0 mt-3 w-56 bg-white dark:bg-slate-800 border border-gray-100 dark:border-slate-700 rounded-2xl shadow-lg overflow-hidden z-50 py-2 origin-top-right"
              >
                <a href="#" class="block px-5 py-3 text-sm font-medium text-gray-700 dark:text-gray-300 hover:bg-indigo-50 dark:hover:bg-slate-700 hover:text-indigo-600 dark:hover:text-indigo-400 transition">
                  My Profile
                </a>
                <a href="#" class="block px-5 py-3 text-sm font-medium text-gray-700 dark:text-gray-300 hover:bg-indigo-50 dark:hover:bg-slate-700 hover:text-indigo-600 dark:hover:text-indigo-400 transition">
                  Settings
                </a>
                <div class="border-t border-gray-100 dark:border-slate-700 my-1"></div>
                <a href="#" class="block px-5 py-3 text-sm font-medium text-red-600 dark:text-red-400 hover:bg-red-50 dark:hover:bg-red-900/20 transition">
                  Sign out
                </a>
              </div>
            </transition>
          </div>

          <button
            @click="toggleTheme"
            class="text-gray-500 cursor-pointer dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-slate-800 focus:outline-none focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-700 rounded-xl text-sm p-2.5 border border-gray-300 dark:border-slate-700 transition"
          >
            <svg v-if="!isDark" class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
              <path d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z"></path>
            </svg>
            <svg v-else class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
              <path d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4 8a4 4 0 11-8 0 4 4 0 018 0zm-.464 4.95l.707.707a1 1 0 001.414-1.414l-.707-.707a1 1 0 00-1.414 1.414zm2.12-10.607a1 1 0 010 1.414l-.706.707a1 1 0 11-1.414-1.414l.707-.707a1 1 0 011.414 0zM17 11a1 1 0 100-2h-1a1 1 0 100 2h1zm-7 4a1 1 0 011 1v1a1 1 0 11-2 0v-1a1 1 0 011-1zM5.05 6.464A1 1 0 106.465 5.05l-.708-.707a1 1 0 00-1.414 1.414l.707.707zm1.414 8.486l-.707.707a1 1 0 01-1.414-1.414l.707-.707a1 1 0 011.414 1.414zM4 11a1 1 0 100-2H3a1 1 0 000 2h1z" fill-rule="evenodd" clip-rule="evenodd"></path>
            </svg>
          </button>
        </div>
      </nav>
    </header>


  </div>
</template>

<style scoped>
/* คุณสามารถใส่ style เฉพาะเจาะจงที่นี่ได้ แต่ส่วนใหญ่จัดการด้วย Tailwind ครบแล้วครับ */
</style>