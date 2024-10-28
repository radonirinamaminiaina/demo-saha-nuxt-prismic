<template>
  <div class="grid grid-cols-2 gap-2">
    <img
      :src="s.gallery.url"
      :alt="s.gallery.alt"
      v-for="(s, index) in slice.items"
      :key="`img__${index}`"
    />
  </div>
</template>

<script setup>
defineProps({ slice: { type: Array } });
</script>
