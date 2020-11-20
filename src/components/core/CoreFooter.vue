<template>
  <div class="core-footer">
    <v-footer color="#272727" padless>
      <v-row justify="center" no-gutters>
        <v-btn
          v-for="link in links"
          :key="link"
          color="#f5deb3"
          text
          rounded
          class="my-2"
          >{{ link }}</v-btn
        >
        <v-col
          class="lighten-1 py-4 text-center"
          style="color:#f5deb3"
          cols="12"
        >
          {{ new Date().getFullYear() }} —
          <strong> Made by 🤦‍♂ Jaeyoung Min</strong>
        </v-col>
      </v-row>
    </v-footer>
  </div>
</template>

<script>
export default {
  name: 'CoreFooter',
  data() {
    return {
      links: ['Home', 'About Me', 'Contact Me'],
    };
  },
};
</script>

<style lang="scss" scoped>
.core-footer {
  background: #050801;
  height: 6vh;
}
</style>
