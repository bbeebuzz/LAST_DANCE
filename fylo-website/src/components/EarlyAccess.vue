<script setup></script>

<template>
  <div
    class="pt-20 px-10 md:px-60 md:py-60 py-20 h-full bg-app text-black dark:text-white"
  >
    <div class="flex justify-center items-center">
      <div class="flex flex-col gap-8">
        <div class="text-4xl font-semibold">Get early access to today</div>
        <div>
          It only takes a minute to sign up and our free starter tier is
          extremely generous. If you have any questions, our support team would
          be happy to help you.
        </div>
        <div class="flex gap-6 md:flex-row flex-col justify-center items-center">
          <input type="text" class="bg-white text-center w-120 md:w-150 text-black placeholder:text-gray-500 border text-xl border-gray-300 focus:outline-none rounded-3xl not-even:focus:ring-2 focus:ring-accent-cyan px-4 py-4" placeholder="email@example.com" />
          <button class="bg-accent-cyan text-white w-120 px-4 py-4 rounded-3xl hover:bg-accent-blue text-center text-xl" >
            Get Started
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
