<template>
  <div class="main">
    <MainBanner />
    <AboutMe ref="aboutEl" />
    <Parallax />
  </div>
</template>

<script>
export default {
  name: 'Main',
  mounted() {
    document.addEventListener('scroll', () => {
      this.$refs.aboutEl.showText(window.scrollY);
    });
  },
  components: {
    MainBanner: () => import('@/components/main/MainBanner.vue'),
    AboutMe: () => import('@/components/main/AboutMe.vue'),
    Parallax: () => import('@/components/main/Parallax.vue'),
  },
};
</script>

<style lang="scss" scoped></style>
