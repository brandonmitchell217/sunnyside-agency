<script setup lang="ts">
defineProps({
  image: String,
  alt: String,
  text: String,
  person: String,
  title: String,
});
</script>
<template>
  <div class="space-y-4 lg:space-y-8 text-center px-2 lg:px-4">
    <NuxtImg :src="image" :alt="alt" class="rounded-full w-16 h-auto mx-auto" />

    <p class="text-base lg:text-lg md:min-h-[100px]">{{ text }}</p>

    <div>
      <h5 class="font-fraunces font-extrabold">{{ person }}</h5>
      <p class="text-darkGrayishBlue font-semibold text-sm">
        {{ title }}
      </p>
    </div>
  </div>
</template>
