<script setup lang="ts">
defineProps<{
  side?: string;
}>();
</script>

<template>
  <div
    class="flex flex-col-reverse justify-center items-center"
    :class="side === 'right' ? 'md:flex-row-reverse' : 'md:flex-row'"
  >
    <div class="w-full md:w-1/2">
      <slot name="left"></slot>
    </div>
    <div class="w-full md:w-1/2">
      <slot name="right"></slot>
    </div>
  </div>
</template>
