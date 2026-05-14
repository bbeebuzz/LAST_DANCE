<script setup>
import { ref } from "vue";

defineProps({
  question: {
    type: String,
    required: true,
  },
});
const faqList = ref([
  { id: 1, question: "What is Bookmark?" },
  { id: 2, question: "How can I request a new browser?" },
  { id: 3, question: "Is ther a mobile app?" },
  { id: 4, question: "What about other Chromium browsers" },
]);
</script>

<template>
  <div id="faq" class="pt-40 md:pt-60 pb-20 px-10 bg-app text-black dark:text-white">
    <div class="flex flex-col justify-center items-center gap-6">
      <div class="text-3xl font-bold text-center">
        Frequently Asked Questions
      </div>
      <div class="text-center">
        Here are some of our FAQs. If you have any other questions you'd like
        answered please feel free to email us.
      </div>
    </div>

    <div class="flex flex-col justify-center items-center mt-10 gap-4">
      <div
        v-for="faq in faqList"
        :key="faq.id"
        class="flex flex-row justify-between items-center w-full max-w-2xl  rounded-lg px-6 py-4 cursor-pointer border-b border-gray-300 dark:border-gray-700"
      >
        <!-- เปลี่ยนจาก faqList[0].question เป็น faq.question -->
        <div class="text-lg font-medium">{{ faq.question }}</div>
        <div class="text-xl font-bold">+</div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
