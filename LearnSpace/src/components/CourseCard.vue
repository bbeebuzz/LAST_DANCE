<script setup lang="ts">
import { ref } from "vue";

// จำลองข้อมูลวิชาเรียน (Mock Data)
const courses = ref([
  {
    id: 1,
    code: "INT250",
    status: "In Progress",
    title: "CSS Framework",
    description:
      "Learn how to build responsive and interactive web applications using Vue.js and Tailwind CSS.",
    progress: 72,
  },
  {
    id: 2,
    code: "INT161",
    status: "In Progress",
    title: "Object-Oriented Programming",
    description:
      "Practice Java programming, object-oriented design, and software development principles.",
    progress: 58,
  },
]);
</script>

<template>
  <div
    class="px-10 bg-white/90 backdrop-blur dark:border-slate-800 dark:bg-slate-900/90 dark:text-white w-screen pb-20 pt-10"
  >
    <div
      class="flex flex-row justify-between items-center gap-10 w-full "
    >
      <div
        v-for="course in courses"
        :key="course.id"
        class="border border-gray-200 dark:border-slate-700 rounded-2xl p-10 h-100 bg-white dark:bg-slate-800 shadow-sm w-full"
      >
        <div class="flex flex-col gap-5 w-full justify-between h-full">
          <div class="flex justify-between items-center">
            <div class="font-medium bg-indigo-100 dark:bg-indigo-500/20 text-indigo-700 dark:text-indigo-300 px-3 py-1 rounded-xl text-sm">{{ course.code }}</div>
            <div class="font-medium bg-yellow-100 dark:bg-yellow-500/20 text-yellow-700 dark:text-yellow-300 px-3 py-1 rounded-xl text-sm">{{ course.status }}</div>
          </div>
          
          <div class="text-3xl font-bold text-gray-900 dark:text-white">{{ course.title }}</div>
          <div class="text-md text-gray-500 dark:text-gray-400">
            {{ course.description }}
            Vue.js and Tailwind CSS.
          </div>
          
          <div class="flex flex-col gap-2 mt-2">
            <div class="font-medium text-gray-900 dark:text-gray-200">Progress: {{ course.progress }}%</div>
            <div class="w-full bg-gray-100 dark:bg-slate-700 rounded-full h-2">
              <div
                class="bg-indigo-600 h-2 rounded-full transition-all duration-500 ease-out"
                :style="{ width: course.progress + '%' }"
              ></div>
            </div>
          </div>
          
          <div class="flex gap-4 mt-4">
            <button class="bg-indigo-600 hover:bg-indigo-700 transition-colors text-white px-5 py-3 rounded-xl font-medium">View Course Details</button>
            <button class="bg-white dark:bg-slate-800 hover:bg-gray-50 dark:hover:bg-slate-700 transition-colors text-gray-900 dark:text-white px-5 py-3 rounded-xl border border-gray-300 dark:border-slate-600 font-medium">Submit Assignment</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>