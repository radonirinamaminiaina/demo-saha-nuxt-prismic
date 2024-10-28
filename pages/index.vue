<template>
  <section>
    <h1 class="text-2xl font-bold mb-8">
      {{ $prismic.asText(homepage.data.title) }}
    </h1>
  </section>
  <section v-if="homepage.data.body.length">
    <component
      v-for="slice in homepage.data.body"
      :is="getSliceComponent(slice.slice_type)"
      :key="slice.id"
      :slice="slice"
    />
  </section>
</template>

<script setup>
const { client } = usePrismic();

const { data: homepage } = await useAsyncData("homepage", () =>
  client.getSingle("homepage")
);

const getSliceComponent = (type) => `section-${type}`;
</script>
