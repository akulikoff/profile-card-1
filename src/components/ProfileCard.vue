<script setup lang="ts">
interface IconsLinks {
  iconName: string;
  iconLink: string;
  iconPath: string;
}
interface CardProps {
  fullName: string;
  position: string;
  summary: string;
  imageUrl: string;
  iconsLinks?: IconsLinks[];
}
defineProps<CardProps>();
</script>

<template>
  <body class="bg-gradient-to-b from-grey-50 to-grey-600">
    <div class="card flex flex-col gap-y-6 justify-center px-4 mx-auto">
      <article class="bg-white text-center rounded-lg p-4 shadow-lg">
        <img
          :src="imageUrl"
          alt="profile image"
          loading="lazy"
          class="size-16 rounded-full content-center mx-auto mb-4"
        />

        <h3 class="text-lg text-neutral-900 font-semibold line-clamp-1">
          {{ fullName }}
        </h3>
        <span class="text-sm text-neutral-600 font-medium">{{ position }}</span>
        <p class="text-neutral-600 my-4 font-medium text-base line-clamp-5">
          {{ summary }}
        </p>
        <button
          class="bg-indigo-700 w-full my-4 leading-10 rounded-sm text-base text-white font-medium outline-4 outline-white focus:outline-4 focus:outline-indigo-200"
        >
          Contact me
        </button>
        <div class="flex flex-row justify-center gap-8 my-4">
          <a
            v-for="link in iconsLinks"
            :key="link.iconName"
            :href="link.iconLink"
            class="size-5 indigo-700 focus:outline-2 focus:outline-indigo-200 hover:bg-gray-100 hover:bg-scale-150 hover:transition hover:duration-300"
          >
            <svg
              aria-hidden="true"
              viewBox="0 0 24 24"
              fill="rgba(67,56,202,1)"
            >
              <path :d="link.iconPath"></path>
            </svg>
          </a>
        </div>
      </article>
    </div>
  </body>
</template>

<style scoped>
body {
  margin: 0;
  font-family: "Noto Sans", sans-serif;
  min-height: 100vh;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-rendering: optimizeLegibility;
}

.card {
  width: 372px;
  margin-top: 200px;
}
.icon {
  width: 24px;
  height: 24px;
  color: #4338ca;
}
* {
  box-sizing: border-box;
}
</style>
