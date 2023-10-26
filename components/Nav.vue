<template>
  <nav class="absolute top-0 left-0 right-0 z-50 py-8">
    <div class="container flex justify-between items-center text-white">
      <a href="/">
        <Logo />
      </a>

      <ul class="hidden md:flex items-center gap-12 text-base">
        <li>
          <NuxtLink to="/">About</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/">Services</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/">Projects</NuxtLink>
        </li>
        <li>
          <NuxtLink
            to="/"
            class="bg-white text-darkDesaturatedBlue border-transparent border uppercase py-2 px-4 rounded-3xl font-bold font-fraunces"
            >Contact</NuxtLink
          >
        </li>
      </ul>
    </div>
  </nav>
</template>
