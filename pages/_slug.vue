<template>
  <div class="container">
    <h1>
      {{ mountain.title }}
    </h1>
    <h3>
      {{ mountain.continent }}
    </h3>
    <img :src="mountain.image" :alt="mountain.title" />
    <p>{{ mountain.description }}</p>
    <nuxt-link to="/">Nack to the list</nuxt-link>
  </div>
</template>

<script>
export default {
  async asyncData({ params }) {
    const mountain = await fetch(
      `https://api.nuxtjs.dev/mountains/${params.slug}`
    ).then(res => res.json());
    return { mountain };
  }
};
</script>

<style>
img {
  max-width: 100%;
}
</style>
