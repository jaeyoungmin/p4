<template>
  <v-app-bar primary dark fixed inverted-scroll>
    <v-btn x-large icon>
      <v-icon color="#f5deb3">mdi-home-outline</v-icon>
    </v-btn>
    <v-spacer></v-spacer>
    <router-link to="/" class="home">Home</router-link>
    <router-link to="/about" class="about">About</router-link>
    <router-link to="/gallery" class="skill">Skill</router-link>
    <router-link to="/gallery" class="portfolio">Portfolio</router-link>
    <router-link to="/contact" class="contact">Contact</router-link>
  </v-app-bar>
</template>

<script>
export default {
  name: 'AppBar',
};
</script>

<style lang="scss" scoped>
a {
  color: wheat;
  font-size: 1.3rem;
  margin-left: 20px;
  text-decoration: none;
}
@media only screen and(max-width: 768px) {
  a {
    font-size: 0.8rem;
  }
}
</style>
