<script setup lang="ts">
import { useFavicon } from "@vueuse/core";

const icon = useFavicon();

icon.value = "/img/favicon-32x32.png";
useSeoMeta({
  title: "Sunnyside Agency",
  ogTitle: "Sunnyside Agency",
  description: "Sunnyside Agency, a creative mock agency.",
  ogDescription: "Sunnyside Agency, a creative mock agency.",
});
</script>
<template>
  <Nav />

  <main class="text-darkDesaturatedBlue">
    <HomeLanding title="We are creatives" />

    <section id="Slaloms">
      <Slalom side="left">
        <template #left>
          <div
            class="flex flex-col items-center md:items-stretch text-center md:text-left gap-3 lg:gap-6 py-[18%] md:py-0 px-[9%] lg:px-[18%]"
          >
            <h2 class="text-3xl lg:text-5xl">Transform your brand</h2>
            <p class="text">
              We are a full-service creative agency specializing in helping
              brands grow fast. Engage your clients through compelling visuals
              that do most of the marketing for you.
            </p>
            <a class="cta">Learn More</a>
          </div>
        </template>
        <template #right>
          <div>
            <NuxtImg
              src="/img/desktop/image-transform.jpg"
              alt="transform egg on yellow background"
              fit="cover"
              width="720"
              height="600"
              class="xl:w-full xl:h-full"
            />
          </div>
        </template>
      </Slalom>
      <Slalom side="right">
        <template #left>
          <div
            class="flex flex-col items-center md:items-stretch text-center md:text-left gap-3 lg:gap-6 py-[18%] md:py-0 px-[9%] lg:px-[18%]"
          >
            <h2 class="text-3xl lg:text-5xl">Standout to the right audience</h2>
            <p class="text">
              Using a collaborative formula of designers, researchers,
              photographers, videographers, and copywriters, we’ll build and
              extend your brand in digital places.
            </p>
            <a class="cta red">Learn More</a>
          </div>
        </template>
        <template #right>
          <div>
            <NuxtImg
              src="/img/desktop/image-stand-out.jpg"
              alt="stand out cup on pink background"
              fit="cover"
              width="720"
              height="600"
              class="xl:w-full xl:h-full"
            />
          </div>
        </template>
      </Slalom>
      <Slalom side="left">
        <template #left>
          <div class="relative">
            <img
              alt="cherries on light greenish background"
              class="w-full h-full object-cover"
              srcset="
                /img/mobile/image-graphic-design.jpg   640w,
                /img/desktop/image-graphic-design.jpg 1440w
              "
            />
            <div
              class="absolute w-full px-8 bottom-6 lg:bottom-12 left-1/2 -translate-x-1/2 space-y-1.5 lg:space-y-6 text-center"
            >
              <h3 class="text-2xl lg:text-3xl">Graphic Design</h3>
              <p class="text min-h-[100px] max-w-[400px] mx-auto">
                Great design makes you memorable. We deliver artwork that
                underscores your brand message and captures potential clients’
                attention.
              </p>
            </div>
          </div>
        </template>
        <template #right>
          <div class="relative">
            <img
              alt="orange on blue background"
              class="w-full h-full object-cover"
              srcset="
                /img/mobile/image-photography.jpg   640w,
                /img/desktop/image-photography.jpg 1440w
              "
            />
            <div
              class="absolute w-full px-8 bottom-6 lg:bottom-12 left-1/2 -translate-x-1/2 space-y-1.5 lg:space-y-6 text-center"
            >
              <h3 class="text-2xl lg:text-3xl">Photography</h3>
              <p class="text min-h-[100px] max-w-[400px] mx-auto">
                Increase your credibility by getting the most stunning,
                high-quality photos that improve your business image.
              </p>
            </div>
          </div>
        </template>
      </Slalom>
    </section>

    <section
      id="Testimonials"
      class="flex flex-col items-center gap-14 lg:gap-20 py-20 md:py-32 lg:py-48"
    >
      <h4
        class="uppercase text-darkGrayishBlue font-extrabold text-xl tracking-[0.25em]"
      >
        Client Testimonials
      </h4>
      <div
        class="container flex flex-col md:flex-row gap-8 md:gap-0 items-center justify-between"
      >
        <div v-for="testimonial in testimonials" :key="testimonial.name">
          <Testimonial
            :image="testimonial.img"
            :alt="testimonial.name + ' profile picture'"
            :text="testimonial.text"
            :person="testimonial.name"
            :title="testimonial.title"
          />
        </div>
      </div>
    </section>

    <section
      id="Image-Gallery"
      class="grid grid-cols-2 grid-flow-row md:grid-cols-4"
    >
      <div v-for="image in galleryImages" :key="image">
        <NuxtImg
          :src="image"
          alt="gallery image"
          fit="cover"
          width="720"
          height="894"
        />
      </div>
    </section>
  </main>

  <Footer />
</template>

<script lang="ts">
export default {
  data() {
    return {
      testimonials,
      galleryImages,
    };
  },
};
const testimonials = [
  {
    name: "Emily R.",
    title: "Marketing Director",
    text: "We put our trust in Sunnyside and they delivered, making sure our needs were met and deadlines were always hit.",
    img: "/img/image-emily.jpg",
  },
  {
    name: "Thomas S.",
    title: "Chief Operating Officer",
    text: "Sunnyside’s enthusiasm coupled with their keen interest in our brand’s success made it a satisfying and enjoyable experience.",
    img: "/img/image-thomas.jpg",
  },
  {
    name: "Jennie F.",
    title: "Business Owner",
    text: "Incredible end result! Our sales increased over 400% when we worked with Sunnyside. Highly recommended!",
    img: "/img/image-jennie.jpg",
  },
] as Array<{
  name: string;
  title: string;
  text: string;
  img: string;
}>;
const galleryImages = [
  "/img/desktop/image-gallery-milkbottles.jpg",
  "/img/desktop/image-gallery-orange.jpg",
  "/img/desktop/image-gallery-cone.jpg",
  "/img/desktop/image-gallery-sugarcubes.jpg",
] as Array<string>;
</script>

<style lang="scss">
a {
  @apply cursor-pointer;
}

p.text {
  @apply text-darkDesaturatedBlue/80 text-sm lg:text-base;
}

a.cta {
  @apply relative w-fit px-[0.15rem] font-fraunces uppercase text-base lg:text-lg xl:text-xl;

  &::after {
    content: "";
    z-index: -1;
    transition: opacity 0.2s ease-in-out;

    @apply absolute w-full opacity-50 rounded-sm bg-yellow left-0 h-[0.3em] bottom-[0.25em] lg:h-[0.4em] lg:bottom-[0.15em];
  }

  &:hover::after {
    @apply opacity-100;
  }
}

a.cta.red {
  &::after {
    @apply bg-softRed;
  }
}
</style>
