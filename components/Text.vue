<template>
  <div v-html="$prismic.asHTML(slice.primary.content)" class="text"></div>
</template>
<script setup>
defineProps({ slice: { type: Array } });
</script>

<style lang="scss" scoped>
.text {
  margin-bottom: 10px;
  ::v-deep(h2) {
    font-size: 24px;
    font-weight: 600;
    margin-bottom: 10px;
  }
}
</style>
