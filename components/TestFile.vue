<script setup lang="ts">
defineProps({
  msg: String,
});
</script>
<template>
  <div class="flex flex-col justify-center items-center w-full py-4">
    <h1 class="text-red-600">{{ msg }}</h1>
    <slot></slot>
  </div>
</template>
