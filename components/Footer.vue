<template>
  <footer class="bg-[#90D4C4] text-darkModerateCyan py-16 md:py-20">
    <div class="flex flex-col items-center justify-center gap-12">
      <div class="space-y-8">
        <NuxtLink to="/">
          <Logo color="hsl(167, 40%, 24%)" class="scale-125 mx-auto" />
        </NuxtLink>

        <ul class="flex items-center gap-12 font-semibold">
          <li>
            <NuxtLink to="/">About</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/">Services</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/">Projects</NuxtLink>
          </li>
        </ul>
      </div>

      <ul class="flex items-center gap-6 text-2xl text-darkDesaturatedCyan">
        <li>
          <a>
            <Icon name="uil:facebook" />
          </a>
        </li>
        <li>
          <a>
            <Icon name="uil:instagram-alt" />
          </a>
        </li>
        <li>
          <a>
            <Icon name="uil:twitter" />
          </a>
        </li>
        <li>
          <a>
            <Icon name="bxl:pinterest" />
          </a>
        </li>
      </ul>
    </div>
  </footer>
</template>

<style scoped lang="scss">
a {
  &:hover {
    color: white;
  }
}
</style>
