<script setup lang="ts">
defineProps({
  title: String,
});
</script>

<template>
  <section class="text-white pt-48 flex flex-col items-center" id="HomeLanding">
    <div class="space-y-20 lg:space-y-28">
      <h1 class="uppercase text-center text-5xl lg:text-7xl tracking-[0.18em]">
        {{ title }}
      </h1>
      <img
        src="/img/icon-arrow-down.svg"
        alt="down arrow"
        class="max-w-full m-auto scale-75 sm:scale-100 xl:scale-125 animate-bounce"
      />
    </div>
  </section>
</template>

<style scoped>
section {
  min-height: 85vh;
  background-image: url("/img/mobile/image-header.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;

  @media (min-width: 640px) {
    min-height: 100vh;
    background-image: url("/img/desktop/image-header.jpg");
  }
}
</style>
