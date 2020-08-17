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
    return fetch("https://api.nuxtjs.dev/mountains")
      .then(res => res.json())
      .then(mountains => ({ mountains }));
  }
};
</script>
