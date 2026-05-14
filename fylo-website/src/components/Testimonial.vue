<script setup>
import { ref } from "vue";

defineProps({
  testimonial: {
    type: String,
    required: true,
  },
});
const testimonialList = ref([
  { id: 1, testimonial: "Fylo has improved our Learr pruductivity by an order of ragnitude. Since making the switch our tearn has becuine a well-uiled collaboration machine." },
  { id: 2, testimonial: "Fylo has improved our Learr pruductivity by an order of ragnitude. Since making the switch our tearn has becuine a well-uiled collaboration machine." },
  { id: 3, testimonial: "Fylo has improved our Learr pruductivity by an order of ragnitude. Since making the switch our tearn has becuine a well-uiled collaboration machine." }
]);
</script>

<template>
  <div
    class="pt-20 px-10 md:px-60 md:py-40 py-20 h-full bg-app-testimonial text-black dark:text-white w-full"
    id="testimonials"
  >
    <div><img src="../assets/bg-quotes.png" alt="" /></div>
    <div class="flex flex-col md:flex-row gap-10 ">
      <div
        class="flex flex-col justify-center p-8 items-center gap-6 dark:bg-gray-800 bg-gray-200 rounded-lg"
        v-for="testimonial in testimonialList"
        :key="testimonial.id"
      >
        <div>
          {{ testimonial.testimonial }}
        </div>
        
        <div class="w-full">
          <div class="flex flex-row gap-4 justify-items items-center ">
            <div>
              <img
                src="../assets/profile-1.jpg"
                alt=""
                class="w-10 h-10 rounded-full"
              />
            </div>
            <div>
              <div>John Doe</div>
              <div>CEO, Company Name</div>
            </div>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<style scoped></style>
