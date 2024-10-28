<template>
  <div>
    <h1 class="text-2xl font-bold mb-8">
      {{ $prismic.asText(blogPage.data.title) }}
    </h1>
    <div v-html="$prismic.asHTML(blogPage.data.content)"></div>
  </div>
</template>

<script setup>
const { client } = usePrismic();

const { data: blogPage } = await useAsyncData("blog_page", () =>
  client.getSingle("blog_page")
);
</script>
