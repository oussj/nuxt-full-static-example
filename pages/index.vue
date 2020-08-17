<template>
  <div>
    <h1>Beautiful mountains</h1>
    <ul>
      <li v-for="mountain in mountains" :key="mountain.slug">
        <nuxt-link :to="mountain.slug"> {{ mountain.title }}</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  asyncData() {
    const mountains = fetch("https://api.nuxtjs.dev/mountains").then(
      res => res.json()
    );
    return { mountains };
  }
};
</script>
