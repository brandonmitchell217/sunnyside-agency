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
  <div class="space-y-4 lg:space-y-8 text-center px-12 sm:px-4">
    <NuxtImg
      :src="image"
      :alt="alt"
      width="60"
      height="60"
      class="rounded-full mx-auto"
    />

    <p class="text-lg font-medium md:min-h-[100px] max-w-[400px] mx-auto">
      {{ text }}
    </p>

    <div>
      <h5 class="font-fraunces font-extrabold">{{ person }}</h5>
      <p class="text-darkGrayishBlue font-semibold text-sm">
        {{ title }}
      </p>
    </div>
  </div>
</template>
