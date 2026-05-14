<script setup lang="ts"></script>

<template>
    <header class="sticky top-0 z-30 border-b border-slate-200 bg-white/90 backdrop-blur dark:border-slate-800 dark:bg-slate-900/90">
        <!-- Navigation -->
         <nav class="mx-auto flex max-w-7xl items-center justify-between px-6 py-4">
            <!-- Logo -->
             <a href="#" class="flex items-center gap-3">
                <div class="flex items-center justify-center h-10 w-10 rounded-2xl bg-indigo-600 text-sm font-bold text-white shadow-sm ">
                    LS
                </div>

                <div>
                    <h1 class="text-lg font-bold text-gray-900 dark:text-white">LearnSpace</h1>
                    <p class="text-sm text-gray-500 dark:text-gray-400">Your learning companion</p>
                </div>
             </a>
             <!-- Desktop Menu -->
              <ul class="hidden items-center gap-8 text-sm">
                <li>
                    <a href="#" class="transition hover:text-indigo-600">Dashboard</a>
                    <a href="#" class="transition hover:text-indigo-600">Courses</a>
                    <a href="#" class="transition hover:text-indigo-600">Assignments</a>
                    <a href="#" class="transition hover:text-indigo-600">Progress</a>
                </li>
              </ul>
         </nav>
    </header>
</template>

<style scoped></style>