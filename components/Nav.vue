<script setup lang="ts">
import {
  useMediaQuery,
  breakpointsTailwind,
  useWindowScroll,
} from "@vueuse/core";
const isTabletScreen = useMediaQuery(
  `(min-width: ${breakpointsTailwind.sm}px)`
);
const isActive = ref<Boolean>(false);
const isScrolled = ref<Boolean>(false);
const { y } = useWindowScroll();

watchEffect(() => {
  if (isTabletScreen.value) {
    isActive.value = false;
  }

  if (y.value > 600) {
    isScrolled.value = true;
  }

  if (y.value < 100) {
    isScrolled.value = false;
  }
});
</script>

<template>
  <nav
    class="fixed top-0 left-0 right-0 z-50 py-8 md:py-12 transition-all duration-500"
    :class="{
      'bg-[#3EBFFF] shadow-lg md:py-8': isScrolled,
      'bg-transparent': !isScrolled,
    }"
  >
    <div class="container flex justify-between items-center text-white">
      <a href="/">
        <Logo />
      </a>

      <ul class="hidden md:flex items-center gap-12 text-base">
        <li>
          <NuxtLink to="/" class="hover:text-white/80">About</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/" class="hover:text-white/80">Services</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/" class="hover:text-white/80">Projects</NuxtLink>
        </li>
        <li>
          <NuxtLink
            to="/"
            class="bg-white text-darkDesaturatedBlue border-transparent border uppercase py-3 px-6 rounded-3xl shadow font-bold font-fraunces hover:bg-white hover:bg-opacity-20 hover:text-white"
            >Contact</NuxtLink
          >
        </li>
      </ul>

      <div
        class="md:hidden cursor-pointer text-white text-3xl transition-colors"
        :class="isActive ? 'text-white/60' : null"
      >
        <Icon name="uil:bars" @click="isActive = !isActive" />
      </div>

      <div
        class="mobileMenu absolute z-50 top-28 left-0 right-0 mx-5 pt-12 pb-16 bg-white text-black"
        :class="isActive == true ? 'block' : 'hidden'"
      >
        <ul
          class="flex flex-col items-center gap-8 text-lg font-semibold text-darkGrayishBlue"
        >
          <li>
            <NuxtLink to="/">About</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/">Services</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/">Projects</NuxtLink>
          </li>
          <li class="mt-4">
            <NuxtLink
              to="/"
              class="bg-yellow text-darkDesaturatedBlue border-transparent border uppercase py-3 px-6 rounded-full shadow font-bold font-fraunces"
              >Contact</NuxtLink
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style scoped lang="scss">
.mobileMenu {
  &::after {
    content: "";
    position: absolute;
    top: -1.5rem;
    right: 0;
    width: 0;
    height: 0;
    border-top: 30px solid transparent;
    border-right: 30px solid white;
    border-bottom: 30px solid transparent;
  }
}
</style>
