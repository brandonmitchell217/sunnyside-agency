<template>
  <section class="text-white pt-48 flex flex-col items-center">
    <div class="space-y-12 md:space-y-20 lg:space-y-28">
      <slot></slot>
      <img
        src="/img/icon-arrow-down.svg"
        alt="down arrow"
        class="max-w-full m-auto scale-75 sm:scale-100 xl:scale-125"
      />
    </div>
  </section>
</template>

<style scoped>
section {
  min-height: 100vh;
  background-image: url("/img/mobile/image-header.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;

  @media (min-width: 640px) {
    background-image: url("/img/desktop/image-header.jpg");
  }
}
</style>
