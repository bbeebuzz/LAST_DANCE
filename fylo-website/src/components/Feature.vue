<script setup>
import iconAccessAnywhere from "../assets/icon-access-anywhere.svg";
import iconSecurity from "../assets/icon-security.svg";
import iconCollaboration from "../assets/icon-collaboration.svg";
import iconAnyFile from "../assets/icon-any-file.svg";

const features = [
  {
    id: 1,
    title: "Access your file from anywhere",
    description:
      "The ability to use a smartphone, tablet, or computer to access your account means your files follow you everywhere.",
    icon: iconAccessAnywhere,
  },
  {
    id: 2,
    title: "Security you can trust",
    description:
      "2-factor authentication and user-controlled encryption are just a couple of the security features we allow to help secure your files.",
    icon: iconSecurity,
  },
  {
    id: 3,
    title: "Collaboration",
    description:
      "Securely share files and folders with friends, family and colleagues for live collaboration. No email attachments required.",
    icon: iconCollaboration,
  },
  {
    id: 4,
    title: "Any file, anywhere",
    description:
      "Whether you're sharing holidays photos or work documents, Fylo has you covered allowing for all file types to be securely stored and shared.",
    icon: iconAnyFile,
  },
];
</script>

<template>
  <div
    id="features"
    class="pt-40 md:pt-60 px-10 bg-app text-black dark:text-white"
  >
    <div
      class="flex flex-row flex-wrap justify-center items-center gap-24 md:gap-40"
    >
      <div
        class="flex flex-col justify-center items-center md:basis-1/3"
        v-for="feature in features"
        :key="feature.id"
      >
        <div class="h-24 flex justify-center items-center">
          <img :src="feature.icon" :alt="`${feature.title} icon`" />
        </div>
        <div class="flex flex-col justify-center items-center mt-6 gap-1">
          <div class="text-xl font-bold">{{ feature.title }}</div>
          <div class="font-medium text-center">
            {{ feature.description }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
