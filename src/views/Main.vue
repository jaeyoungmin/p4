<template>
  <div class="main">
    <MainBanner />
    <AboutMe ref="aboutEl" />
    <Features ref="featuresEl" />
    <Parallax />
  </div>
</template>

<script>
export default {
  name: 'Main',
  mounted() {
    document.addEventListener('scroll', () => {
      this.$refs.aboutEl.showText(window.scrollY);
      this.$refs.aboutEl.positionFix(window.scrollY);
      this.$refs.featuresEl.showCard(window.scrollY);
    });
  },
  components: {
    MainBanner: () => import('@/components/main/MainBanner.vue'),
    AboutMe: () => import('@/components/main/AboutMe.vue'),
    Features: () => import('@/components/main/Features.vue'),
    Parallax: () => import('@/components/main/Parallax.vue'),
  },
};
</script>

<style lang="scss" scoped></style>
