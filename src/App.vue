<script setup lang="ts">
import ProfileCard from "./components/ProfileCard.vue";
const data = {
  fullName: "Sara Dole",
  position: "Front End Engineer @ Microsoft",
  summary:
    "I turn coffee into bugs which are fixed by someone else. Certified Stack Overflow and ChatGPT developer.",
  imageUrl: "src/assets/img/profile.png",
};
</script>

<template>
  <ProfileCard v-bind="data" />
</template>

<style scoped></style>
